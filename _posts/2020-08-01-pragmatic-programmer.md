# The Pragmatic Programmer

[The Pragmatic Programmer](https://www.amazon.com/Pragmatic-Programmer-journey-mastery-Anniversary/dp/0135957052/ref=pd_lpo_14_t_0/130-7504865-3952829?_encoding=UTF8&pd_rd_i=0135957052&pd_rd_r=3a41bfb2-4fe2-414d-afd0-26eed92dc2dd&pd_rd_w=CgQ5N&pd_rd_wg=JdyCQ&pf_rd_p=7b36d496-f366-4631-94d3-61b87b52511b&pf_rd_r=PG6YT8Z0XJAWXC312HX4&psc=1&refRID=PG6YT8Z0XJAWXC312HX4) has been the book sitting on my to-read list for a while, and I finally got a chance to finish it recently. I found the book covers comprehensively on important aspects of being a software engineer, which makes it a very helpful book to read if you're new to the software development world. However, for people who's in this software world longer like I am, the book might not provide much helpful knownledge as I found I already know most of the knownledges described in the book.

Anyway, I still found the following topics that I haven't known much about before my reading the book. I'm sharing them in this post.

## Tracer (Bullet) Code

In my understanding, **tracer code is the minimal version that works end-to-end**."Once you have achieved an end-to-end connection among the components of your system, you can check how close to the target you are, adjusting if necessary. Once you're on target, adding functionality is easy." Tracer code helps users to get see something working early, helps developers to build a structure to work in, and bring the project with an integration platform which is something you can demostrate. Unlike prototype, tracer code isn't disposable as it's lean but complete.

In my opinion, people should use tracer code when they are building something brand new or trying to add a bigger block into an existing code. Instead of designing all details beforehand, tracer code helps you make everything be connected first, and you can figure out the details later, independently.

## Broken Windows Theory

"**One broken window, left unrepaired for any substantial length of time**, instills in the inhabitants of the building a sense of abandonment - a sense that the powers that be don't care about the building. So, **another window gets broken**." Broken Windows Theory tells software engineers that if a bad smell is left somewhere in the codebase and not repaired, that code will soon become worse as people would put less and less care over time. The simple advise from the book is not to leave "broken windows" (bad designs, wrong decisions, or poor code) unrepaired.

I found this theory is valid. Say, if you found a bad code which is hard to understand, has a super long function, and contains logic that 'maybe' haven't been used for years. Then, you're asked to add some code here for a new functionality. You'll think that it's already very hard to understand the existing code, it's even harder to write high-quality code. So, you degrade your standard of the code quality, just to make sure things can work within a reasonble time. Eventually, more broken windows appear in this code.

## Conclusion

In this post, I shared two topics that I have't heard of before reading [The Pragmatic Programmer](https://www.amazon.com/Pragmatic-Programmer-journey-mastery-Anniversary/dp/0135957052/ref=pd_lpo_14_t_0/130-7504865-3952829?_encoding=UTF8&pd_rd_i=0135957052&pd_rd_r=3a41bfb2-4fe2-414d-afd0-26eed92dc2dd&pd_rd_w=CgQ5N&pd_rd_wg=JdyCQ&pf_rd_p=7b36d496-f366-4631-94d3-61b87b52511b&pf_rd_r=PG6YT8Z0XJAWXC312HX4&psc=1&refRID=PG6YT8Z0XJAWXC312HX4): Tracer Code and Broken Windows Theory. Lastly, I want to share two things that might make you reconsider if you want to read this book or not. First, the book sometimes uses language specific examples (Mixin, Clojure, etc) to explain some general concepts which made me hard to follow. Second, most of the concepts described in the book are generic and maybe you don't need to a book to learn them.