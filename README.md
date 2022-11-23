# Laravel-8-Resource-Routing

### Resource Route: routes/web.php

```
use App\Http\Controllers\BlogController;
Route::resource('blogs', BlogController::class);
```
OR
```
Route::resources([
	'photos' => PhotoController::class,
  'posts' => PostController::class,
]);
```
OR

```
Route::resource('blogs', App\Http\Controllers\BlogController::class);
```
Now, you can run bellow command and check route lists:

```
php artisan route:list
```

Domain | Method | URI | Name | Action | Middleware 
--- | --- | --- | --- |--- |--- |
| | GET\|HEAD | api\/user | | Closure | api,auth:api
| | GET\|HEAD | blogs | blogs.index | App\Http\Controllers\BlogController@index | api,auth:api
| | POST | blogs | blogs.store | App\Http\Controllers\BlogController@store | web
| | GET\|HEAD | blogs/create | blogs.create | App\Http\Controllers\BlogController@create | web
| | GET\|HEAD | blogs/{blog} | blogs.show | App\Http\Controllers\BlogController@show | web
| | PUT\|PATCH | blogs/{blog} | blogs.update | App\Http\Controllers\BlogController@update | web
| | DELETE | blogs/{blog} | blogs.destroy | App\Http\Controllers\BlogController@destroy | web
| | GET\|HEAD | blogs/{blog}/edit | blogs.edit | App\Http\Controllers\BlogController@edit | web

### Resource Controller Command: app/Http/Controllers/BlogController.php
```
php artisan make:controller BlogController --resource
```

```
<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;

class BlogController extends Controller
{
    /**
     * Display a listing of the resource.
     *
     * @return \Illuminate\Http\Response
     */
    public function index()
    {
        //
    }

    /**
     * Show the form for creating a new resource.
     *
     * @return \Illuminate\Http\Response
     */
    public function create()
    {
        //
    }

    /**
     * Store a newly created resource in storage.
     *
     * @param  \Illuminate\Http\Request  $request
     * @return \Illuminate\Http\Response
     */
    public function store(Request $request)
    {
        //
    }

    /**
     * Display the specified resource.
     *
     * @param  int  $id
     * @return \Illuminate\Http\Response
     */
    public function show($id)
    {
        //
    }

    /**
     * Show the form for editing the specified resource.
     *
     * @param  int  $id
     * @return \Illuminate\Http\Response
     */
    public function edit($id)
    {
        //
    }

    /**
     * Update the specified resource in storage.
     *
     * @param  \Illuminate\Http\Request  $request
     * @param  int  $id
     * @return \Illuminate\Http\Response
     */
    public function update(Request $request, $id)
    {
        //
    }

    /**
     * Remove the specified resource from storage.
     *
     * @param  int  $id
     * @return \Illuminate\Http\Response
     */
    public function destroy($id)
    {
        //
    }
}
```



















