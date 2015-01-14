Формы и валидация

Формы бывают нескольких видов. Первый:

	d()->post('/news/',function(){

		//Проверяем значения
		if(){
			d()->notice = 'Ошибка!';
		}
		d()->next();
	});

	d()->route('/news/',function(){

	 	print d()->notice;
		print file_get_contents('app/news/form.html');
	});

Второй (ajax и iframe):

	d()->post('/news/',function(){

		//Проверяем значения
		if(){
			d()->notice = 'Ошибка!';
		}
		print d()->notice;
	});


	d()->get('/news/',function(){
		print file_get_contents('app/news/form.html');
	});