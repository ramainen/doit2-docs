Для таких вещей, как `{title.h}` или `d()->mail()` или `preview` есть заранее подготовленные функции-помощники.

Для того, чтобы добавить свою функцию, надо создать класс, возвращающий её с именем `FunctionFactory` (например `UrlFactory` или `PreviewFactory`).

Три варианта использования (просто функция, объект, объект-синглтон)

Например, функция d()->h() (просто функция)

### `/lib/HFactory.php`

	namespace doit;
	class HFactory(){
		static function create(){
			return function($text){
				return htmlspecialchars ($text);
			}
		}
	}

Объект-синглтон (например, seo)

### `/lib/SeoFactory.php`

	namespace doit;
	class SeoFactory(){
		static function create(){
	
			$seo = new Seo();
			$seo->init();
			return $seo;
		}
	}

Просто объект (например, `d()->preview()`)

### `/lib/PreviewFactory.php`

	namespace doit;
	class PreviewFactory(){
		static function create(){
	
			return function(){
				$imagine = new Imagine;
				$imagine->resize;
				return $imagine;
			}
		}
	}

Минусы - больше кода, больше всякой фигни в папке lib

Плюсы: Можно сделать модуль в composer, не нужна папка helpers