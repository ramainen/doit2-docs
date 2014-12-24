Для таких вещей, как `{title.h}` или `d()->mail()` или preview есть заранее подготовленные функции-помощники.

Для того, чтобы добавить свою функцию, надо создать файл с её именем в папке `/helpers/`

Три варианта использования (просто функция, объект, объект-синглтон)

Например, функция `d()->h()` (просто функция)

### `/helpers/h.php`

	namespace doit;
	
	return function($text){
		return htmlspecialchars ($text);
	}

Объект-синглтон (например, seo)

### `/helpers/seo.php`

	namespace doit;
	
	$seo = new Seo();
	$seo->init();
	return $seo;

Просто объект (например, `d()->preview()`)

### `/helpers/preview.php`

	namespace doit;
	
	return function(){
		$imagine = new Imagine;
		$imagine->resize;
		return $imagine;
	}

Минусы - нельзя helpers поместить в composer в качестве модуля. Предполагается, что все системные функции (`preview`, `h`, `url` и т.д.) уже объявлены в коде.