# Методика измерения реакции аудитории на котент в YouTube (на примере контента о картах Таро)

В данной работе мы разработали методику измерения реакции аудитории, с помощью которой можно комплексно измерить реакцию пользователей на контент с учетом как числовых, так и текстовых данных. Фокус работы был сделан на сравнении различных моделей статистического анализа текстовых данных, в связи с трудностью их учета и отсутствием универсального подхода. Наш инструмент измерения пригоден для анализа реакции на любой контент в YouTube. В связи с социальной значимостью, а также личными исследовательскими интересами, в качестве примера мы опробовали методику на контенте о картах Таро. 
Мы изучили два типа моделей, пригодных для анализа текстовых данных – модели тематического моделирования (LSA, LDA и NMF) и сентимент анализа (наивный Байес-Бернулли и мультиномиальный наивный байесовский классификатор, метод опорных векторов, логистическая регрессия). В ходе изучения предшествующих работ на эту тему мы определили, что тематическое моделирование и сентимент анализ возможно применять в социологических исследованиях, так как данные методы являются полезными и удобными инструментами анализа текстовых данных. Так, тематическое моделирования отражает структуру текста: позволяет автоматически выделять ряд тем из текстового документа. Сентимент анализ же дает возможность определить отношение людей к определённым объектам, которые были описаны в тексте. Иными словами, эти типы моделей выполняют важные, но разные функции анализа текстовых данных.
В результате эмпирического сравнения моделей тематического моделирования в качестве лучшей модели с точки зрения значения согласованности и логичности получившихся топиков мы выбрали модель LDA. Таким образом, наша гипотеза, основанная на теоретическом сравнении моделей тематического моделирования, подтвердилась. После обучения моделей сентимент анализа в качестве лучшей с точки зрения ее прогностической силы мы выбрали модель, обученную с использованием классификатора наивного Байес-Бернулли. Для данной модели наблюдалось достаточно большая доля правильно предсказанных объектов (70%), а также одинаковая точность предсказания как негативного, так и позитивного класса (также 70%). Однако, предполагалось, что лучшей моделью сентимент анализа будет модель, основанная на методе опорных векторов – наша гипотеза не подтвердилась. Поэтому для создания совмещенной модели, с помощью которой возможно автоматически выделять топики из текста и их настроения, мы скомбинировали две наилучшие модели: модель тематического моделирования LDA и модель сентимент анализа с использованием классификатора наивного Байес-Бернулли. В результате для каждого топика мы рассчитали среднее значение тональности, что позволяет говорить о выраженности позитивного или негативного настроения для каждой темы. 
Практическая ценность разработанной нами методики состоит в том, что ее могут использовать исследователи в сфере социальных наук, не обладающие знаниями в области программирования, так как на выходе методика представляет из себя автоматический инструмент измерения реакции аудитории.
Для обучения моделей сентимент анализа мы использовали корпус размеченных данных «RuTweetCorp», который содержит короткие тексты из социальной сети Twitter и их тональную метку. Дальнейшее развитие нашей работы мы видим в том, чтобы собрать большой корпус комментариев под различными видео в YouTube. Затем, для достижения согласованности тональной оценки, разметить одни и те же комментарии группой исследователей. В результате на размеченных комментариях из YouTube обучить модели сентимент анализа. Мы полагаем, что это позволит повысить прогностическую силу моделей. Стоит отметить, что лексика пользователей Twitter приближена к языку, на котором общаются пользователи YouTube. Однако, мы осознаем, что аудитория YouTube может использовать специфические выражения, которые не характерны для пользователей других социальных сетей. Поэтому обучение моделей сентимент анализа на размеченном корпусе «RuTweetCorp» является ограничением нашего исследования. В будущем мы также намерены обучить модели, с помощью которых можно будет предсказать не только бинарное, но и множественное настроение в комментариях (например, с пятью градациями, где 1 - очень негативное, а 5 - очень позитивное). На наш взгляд, это позволит более детально изучить отношение аудитории к изучаемому контенту на YouTube.

