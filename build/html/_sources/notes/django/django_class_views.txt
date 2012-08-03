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