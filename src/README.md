# Create Reat App

Cтраница была создана с помощью React.js. 
- import React from "react" . Мы этой строкой импортируем React из библиотеки "react" , которая находится в папке node_modules.

Страница включает в себя Login form. В этом проекте были использованы такие пакеты , как:
</br>

- @fortawesome/fontawesome-svg-core": "^1.2.32",

- "@fortawesome/free-solid-svg-icons": "^5.15.1",

- "@fortawesome/react-fontawesome": "^0.1.13",

- yup,

- formik,

## Code Example

С помощью React.js и пакетов была создана форма входа . На этой форме присутствуют значки , которые были созданы с помощью:
- @fortawesome/fontawesome-svg-core": "^1.2.32",
- "@fortawesome/free-solid-svg-icons": "^5.15.1",
- "@fortawesome/react-fontawesome": "^0.1.13",

Пример кода:

//code

    <FontAwesomeIcon icon={faTimes}/>
    <FontAwesomeIcon icon={faCheck}/>
    <FontAwesomeIcon icon={faUser}/>
    <FontAwesomeIcon icon ={faLock}/>

и также сама форма была создана с помощью: 
- yup (Yup — библиотека, которая является валидатором для модели, которую мы сами и создаем с помощью Yup.)
- formik (Formik — библиотека, помогающая работать с формами. Она упрощает получение данных из формы, валидацию данных, вывод сообщений об ошибках и многое другое)

Пример кода 
//code

    const SignupSchema = Yup.object().shape({
    email: Yup.string()
    .email("Invalid e-mail")
    .required("Invalid e-mail"),
    password: Yup.string()
    .min(6, "Invalid password")
    .max(24, "Invalid password")
    .required("Invalid password"),
    });

    <Formik
        initialValues={{
        email: "",
        password: "",
        }}
        validationSchema={SignupSchema}
        onSubmit={(data) => {
        console.log(data);
        }}
    >
        {({ touched, errors }) => (
        <Form className="form">
        <div>
            <div className="field-block">
                <FontAwesomeIcon icon={faUser}/>
                <Field className={touched.email && (touched.email && errors.email ? "error" : "success") } name="email" type="email" placeholder="E-mail"></Field>
                {touched.email && errors.email && (
                <span className="errorEmail-Text"><div className="error">{errors.email}</div></span>
                )}
                {touched.email && errors.email && (
                <FontAwesomeIcon icon={faTimes}/>
                )}
                {touched.email && !errors.email && (
                <FontAwesomeIcon icon={faCheck}/>
                )}
            </div>
        </div>
        <div>
            <div className="field-block">
                    <FontAwesomeIcon icon ={faLock}/>
                    <Field className={touched.password && (touched.password && errors.password ? "error" : "success") } name="password" type="password" placeholder="Password"></Field>
                    {touched.password && errors.password && (
                    <span className="errorPassword-Text"><div className="error">{errors.password}</div></span>
                    )}
                    {touched.password && errors.password && (
                    <FontAwesomeIcon icon={faTimes}/>
                    )}
                    {touched.password && !errors.password && (
                    <div className="success">{!errors.password}</div>
                    )}
                    {touched.password && !errors.password && (
                    <FontAwesomeIcon icon={faCheck}/>
                    )}
            </div>
        </div>
        <button type="submit" >Login</button>
        </Form>
        )}
    </Formik>

## Prerequisites
Для установки пакетов мы используем npm . Это менеджер пакетов, входящий в состав Node.js. Установка пакета производится при помощи команды: npm install <packagename> .Все доступные для установки пакеты и их краткое описание: npm search.

## Installation
- import React from "react"
- import './App.css';
- import { faUser } from "../node_modules/@fortawesome/free-solid-svg-icons";
- import { faLock } from "../node_modules/@fortawesome/free-solid-svg-icons";
- import {faCheck } from "../node_modules/@fortawesome/free-solid-svg-icons";
- import {faTimes } from "../node_modules/@fortawesome/free-solid-svg-icons";
- import { FontAwesomeIcon } from "../node_modules/@fortawesome/react-fontawesome";
- import { Formik, Field, Form} from "formik";
- import * as Yup from "yup";

Для того , чтобы импортировать пакеты , мы должны их установить с помощью npm . К примеру: npm install --save @fortawesome/free-solid-svg-icons. Где --save создает зависимость в package.json. Когда мы установили эти пакеты , мы их импортируем , и , чтобы запустить проект в терминале , вводим npm start(Запускает приложение в режиме разработки.) Если вы внесете правки, страница перезагрузится.
Вы также увидите любые ошибки ворса в консоли.</br>
Для просмотра результата формы откройте [http://localhost:3000](http://localhost:3000) в браузере.

## Tests
- npm test
Запускает тестовый раннер в интерактивном режиме часов.

## Built With
- React — JavaScript-библиотека с открытым исходным кодом для разработки пользовательских интерфейсов. 

## Versioning
- React следует семантическому управлению версиями (semver).

## Author
- Ярослав Цыбух (проект my-react-app)

## License
Этот проект находится под лицензией MIT License.