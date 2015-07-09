# PR2_Zykova_Lab_Rab_2
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
 <title>Примеры. Добавление прямоугольника на карту.</title>
 <meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
 <!--
 Подключаем API карт 2.x
 Параметры:
 - load=package.full - полная сборка;
 - lang=ru-RU - язык русский.
 -->
 <script src="http://api-maps.yandex.ru/2.0/?load=package.full&lang=ru-RU"
 type="text/javascript"></script>
 <script type="text/javascript">
 // Как только будет загружен API и готов DOM, выполняем инициализацию
 ymaps.ready(init);
 function init() {
 var myMap = new ymaps.Map('map', {
 center: [-22.61, 17.08],
 zoom: 8
 }),
 // Создаем первый прямоугольник
 myRect = new ymaps.Rectangle([
 // Задаем координаты диагональных углов прямоугольника
 [-22.47, 17.16],
 [-22.641, 16.98]
 ]),
 // Альтернативный способ создания прямоугольника:
 // создаем геообъект с типом геометрии "прямоугольник".
 myGeoObject = new ymaps.GeoObject({
// Задаем модель геообъекта.
// Модель = геометрия + свойства гообъекта.
// Геометрия = тип геометрии + координаты геообъекта.
geometry: {
 // Тип геометрии - прямоугольник
 type: "Rectangle",
// Координаты
coordinates: [
 [-22.61, 17.08],
 [-22.61, 17.08]
 ]
 }
 });
 myMap.geoObjects.add(myRect)
 .add(myGeoObject);
 }
 </script>
</head>
<body>
<h2>Добавление прямоугольника на карту</h2>
<div id="map" style="width:600px;height:400px"></div>
</body>
</html>
