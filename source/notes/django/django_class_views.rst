========================
Django Class Based Views
========================


Views
-----

Views::

    from django.shortcuts import render
    from blog.models import *
    from django.views.generic import DetailView, ListView
    
    
    class PostDetailView(DetailView):
        context_object_name = "post"
        template_name = "blog/post_detail_view.html"
        queryset = Post.objects.all()
        
    class PostListView(ListView):
        context_object_name = "posts"
        template_name = "blog/post_list_view.html"
        queryset = Post.objects.all()
        paginate_by = 6
        
    class HomePageView(ListView):
        context_object_name = "posts"
        template_name = "blog/home.html"
        queryset = Post.objects.all()
        
Urls
----

Urls::

    from django.conf.urls import patterns, include, url
    from blog.views import PostDetailView, PostListView
    
    
    urlpatterns = patterns('',  
        
        url(r'^posts/$', PostListView.as_view(), name="post_list_view"),
        url(r'^posts/(?P<slug>[-\w]+)/$', PostDetailView.as_view(), name="post_detail"),
    )

Mixins
------

Mixins can easily be added to class based views to extend and inherit common functionality::

    from django.utils.decorators import method_decorator
    from django.contrib.auth.decorators import login_required
    from django.core.urlresolvers import reverse_lazy
    from kstate.common.auth.decorators import group_required
    STAFF_LOGIN = reverse_lazy("login")

    class StaffRequiredMixin(object):
        """
        View mixin for the staff application.  Requires someone to be a staff member.

        """

        @method_decorator(login_required(login_url=STAFF_LOGIN))
        @method_decorator(group_required("Staff"))
        def dispatch(self, *args, **kwargs):
            return super(StaffRequiredMixin, self).dispatch(*args, **kwargs)


    class AdminRequiredMixin(object):
        """
        View mixin for staff app. Required admin group.
        """

        @method_decorator(login_required(login_url=STAFF_LOGIN))
        @method_decorator(group_required("Admin"))
        def dispatch(self, *args, **kwargs):
            return super(AdminRequiredMixin, self).dispatch(*args, **kwargs)