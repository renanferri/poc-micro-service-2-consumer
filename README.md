## POC - MICRO SERVICE 2 => CONSUMER

The idea is this project be a micro service as consumer. It recive a message from rabbitmq in a default queue.

The other project named "poc-micro-service-1-producer", will send the message to rabbitmq and this micro-service will consume it.



<p><b>How it works:</b></p>

In both projects it is necessary to use this library:
https://github.com/vyuldashev/laravel-queue-rabbitmq

In .env.example copy configs about rabbimt to .env
Change in .env to QUEUE_CONNECTION=rabbitmq

In website: https://www.rabbitmq.com/docs/download you need to execute docker run in the example there to up a container of rabbitmq

Example:
docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.13-management (By this container will traffic the comunication queue.)



Finally, you just need execute a php artisan tinker in the terminal and after execute php artisan queue:work

So, the message arrived in localhost:15672 (rabbitmq) will be consumed in the worker that will be listening the rabbitmq








