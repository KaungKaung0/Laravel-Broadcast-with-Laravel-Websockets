# Laravel Broadcast with Laravel Websockets

### Used Package
- [Laravel Websockets](https://beyondco.de/docs/laravel-websockets/basic-usage/pusher).
- Laravel Echo.

### Note

- You need to start laravel websocket server and define pusher variables in .env file.
- For frontend services, it use **Laravel Echo**,which is defined in `resources/js/bootstrap.js`.
- **Whenever you update bootstrap.js**, please run `npm run dev`.
- Broadcast channel must be defined in `routes\channels.php` and must set which user can get broadcast.In this example, we set to get broadcast on **user's id 1**.
```
Broadcast::channel('testchannelevent', function ($user) {
    return (int) $user->id === 1;
});

```
- Event must **implement ShouldBroadcast** Interface

### Example

- Start laravel project and websocket server
```
php artisan serve
php artisan websockets:serve

```