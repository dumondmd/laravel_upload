<p align="center"><img src="https://res.cloudinary.com/dtfbvvkyp/image/upload/v1566331377/laravel-logolockup-cmyk-red.svg" width="400"></p>

# Laravel Upload

## Pasta para armazenar arquivo dentro do projeto

Criando link da pasta Storage para a pasta Public (onde estão o css/js)

```
php artisan storage:link
```

## Armazenando arquivo

No **Controller**

Dentro do *store*
```
$path = $request->file('arquivo')->store('imagens', 'public');
$post->arquivo = '$path';
```

## Na **view**

```
<form method="POST" action="/" enctype="multipart/form-data">
@csrf
```

# Tinker

Abrindo Tinker
```
php artisan tinker
```

Chamando todos registros

```
$posts = App\Post::all()
```

# Pegando caminho absoluto

Pegando caminho absoluto para fazer download

```
$path = Storage::disk('public')->getDriver()->getAdapter()->applyPathPrefix($post->arquivo);
```