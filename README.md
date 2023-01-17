﻿# react-Router
# React Router
    В React имеется своя система маршрутизации, которая позволяет
    сопоставлять запросы к приложению с определенными компонентами. 
    Ключевым звеном в работе маршрутизации является модуль react-router, 
    который содержит основной функционал по работе с маршрутизацией.
# Router
    Маршрутизатор — это аппаратное устройство, предназначенное для приема, анализа и 
    перемещения входящих пакетов в другую сеть. Router определяет набор маршрутов и,
    когда к приложению, приходит запрос, то Router выполняет сопоставление запроса с маршрутами.
    И если какой-то маршрут совпадает с URL запроса, то этот маршрут выбирается для обработки запроса.

    
# Path
    Относительные пути
    — Oтносительные пути. Раньше в пропсе path у компонентов Route
    нужно было указывать полный путь Теперь вам достаточно указать 
    относительный путь в пропсе path. Он будет автоматически добавлен к
    пути родительского роута. Например, компонент Courses теперь можно написать так:
    
# Before 
    <Switch>
        <Route path=”/courses/list” component={CoursesList} />
        <Route path=”/courses/:id” component={CoursePage} />
    </Switch>

# After
    <Routes>
        <Route path=”list” element={<CoursesList />} />
        <Route path=”:id” element={<CoursePage />} />
    </Routes>
    
# Element вместо Component / render
    Раньше в компоненте Route был выбор: либо указать компонент для рендера,
    либо передать render-prop функцию. В первом случае код выглядит красиво:
    Но у него есть существенный недостаток. Вы не могли прокинуть дополнительные
    пропсы в компонент из родителя. Проблема решалась использованием render-функции:
    В новой версии роутера даже этого делать не придется. Оба этих пропса заменены на\
    один — element. В него можно передать любой JSX-элемент. Пример выше в таком случае будет выглядеть так:
    
# Before
    <Route path={urls.courses} render={props => <CoursesList {...props} otherProp={myProp} />} />
    
# After
    <Route path={urls.courses} element={<CoursesList otherProp={myProp} />} />
