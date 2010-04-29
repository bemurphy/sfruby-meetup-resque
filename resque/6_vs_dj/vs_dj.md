!SLIDE smbullets

# Resque vs DelayedJob

* Resque supports multiple queues
* DelayedJob supports finer grained priorities
* Resque workers are resilient to memory leaks / bloat
* DelayedJob workers are extremely simple and easy to modify
* Resque requires Redis
* DelayedJob requires ActiveRecord
* Resque can only place JSONable Ruby objects on a queue as arguments
* DelayedJob can place any Ruby object on its queue as arguments
* Resque includes a Sinatra app for monitoring what's going on
* DelayedJob can be queried from within your Rails app if you want to add an interface

!SLIDE smbullets

# Choose Resque if...

* You need multiple queues
* You don't care / dislike numeric priorities
* You don't need to persist every Ruby object ever
* You have potentially huge queues
* You want to see what's going on
* You expect a lot of failure / chaos
* You can setup Redis
* You're not running short on RAM

!SLIDE smbullets

# Choose DelayedJob if...

* You like numeric priorities
* You're not doing a gigantic amount of jobs each day
* Your queue stays small and nimble
* There is not a lot failure / chaos
* You want to easily throw anything on the queue
* You don't want to setup Redis

!SLIDE bullets

# Performance - Enqueueing Jobs


* delayed job - 200 jobs/sec
* rabbitmq - 2500 jobs/sec
* resque - 3800 jobs/sec
* beanstalk - 9000 jobs/sec

*source: http://adamblog.heroku.com/past/2010/4/24/beanstalk_a_simple_and_fast_queueing_backend/
