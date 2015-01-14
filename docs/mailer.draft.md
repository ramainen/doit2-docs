Использование почты

$message = d()->message;
$message->setTo('mail@mail.ru');
$message->setSubject('Привет!');

d()->mailer->send($message);



$message = d()->message;
$message->setTo('mail@mail.ru');
$message->setSubject('Привет!');

$message->subject = 'Привет!';



$message->send();





