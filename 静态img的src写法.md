例如car detail页面模板car.html中，

车头 `<img src="../img/car_gray.png">`是相对模板的路径写法，设备中无法显示

如果按照绝对路径 `src="/img/car_gray.png"` 也不行。

在看过同样问题的回答 [ionic中，图片无法显示](http://segmentfault.com/q/1010000002645525?sort=created) 后，
试试  `src="img/car_gray.png"`， 在chrome和设备中显示正常。
