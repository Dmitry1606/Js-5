# Js-5
// Задание 1
// Дан объект:
// let user = { name: 'Tom', age: 20, isMarried: false }
// Cформировать массив строк вида "имя_поля - значение_поля":
// ['name - Tom', 'age - 20', 'isMarried - false']
// Реализовать это в виде функции, которая принимает объект и возвращает массив. Использовать цикл for-in

let user = { name: 'Tom', age: 20, isMarried: false }
function accepptsObject(Object) {
    let massiv = [];
    for (let key in Object) {
        massiv.push(`${key}-${Object[key]}`);
    }
    return massiv
}
console.log(accepptsObject(user))


// Задание 2.1
// Написать функцию, которая принимает два параметра и складывает их.
// Предусмотреть проверку на тип данных. Если хоть один из параметров не является числом, должно выводиться ообщение об ошибке.
// Примеры результатов вызова функции:
// sum(2,4); // 6
// sum('d',4); // введенные данные не являются числами
// sum(1, [2]); // введенные данные не являются числами
// sum(1); // введите два параметра
// sum(); // введите два параметра

// Задание 2.2
// Доработать задание 2.1 с проверкой на вызов функции без аргументов или с одним аргументом.
// sum(1)// введите два параметра
// sum() // введите два параметра

function sumOfNumbers(num1, num2) {
    if (typeof num1 !== 'number' || typeof num2 !== 'number') {
        console.log('введенные данные не являются числами')
    }
    else {
        return num1 + num2
    }
    if (arguments.length < 2);
    console.log('сообщение об ошибке')


}
console.log(sumOfNumbers())



//Задание 3
// Создать функцию "угадай число". Она принимает число от 1 до 10 (обязательно проверить, что число не больше 10 и не меньше 0). Генерирует рандомное число от 1 до 10 и сравнивает с заданным числом.
// Если они совпали, то возвращает “Вы выиграли”, если нет - то “Вы не угадали, ваше число -  ...,  а выпало число ...”
// Функция создания случайного числа уже была ранее в материалах, в задаче по созданию случайного цвета.
// Написать функцию в стрелочном синтаксисе.

function getRandomInteger(min, max) {
    return Math.floor(Math.random() * (max - min)) + min;
}


let guessNumber = (number) => {
    if (number > 0 && number < 10) {
        let randomNumber = getRandomInteger(1, 10)
        if (randomNumber == number) {
            console.log('Вы выиграли')
        } else {
            (randomNumber !== number)
            console.log(`вы не угадали, ваше число ${randomNumber}`)
        }


    }

}
guessNumber(5);


// Задание 4
// Напишите функцию copyArr(arr), которая копирует массив, не изменяя оригинал. Используйте подходящий метод массива.


function copyArr(arr) {
    let newArr = arr.map(item => item)
    return () => {
        console.log(newArr)
    }
}



// Задание 5
// На странице в html задать список элементов li с числами. Джававскриптом нужно выбрать из этого списка четные числа и создать из них массив. Затем, используя метод forEach, создать из массива новый спсок элементов li и поместить эти элементы в исходный тег ul. Для обхода через querySelectorAll использовать цикл for-of (forEach работать не будет).

let listItems = document.querySelectorAll('li')
let massiv = []
for (let i = 0; i < listItems.length; i++) {
    if (listItems[i].innerText % 2 === 0) {
       massiv.push(listItems[i].innerText)
    }
}
console.log(massiv)






// Задание 6
// 1) Создать разметку формы с инпутом для текста и селектом для категории (добавить несколько option с текстом Категория 1, Категория 2, Категория 3). Опшны создайте и добавьте в select через цикл.
// 2) Под формой должны должен быть список ul. В этот список каждую секунду добавляется новый элемент li с произвольным текстом (напр. Hello). Для этого можно использовать функцию setInterval:
// Почитайте об этой функции здесь: https://learn.javascript.ru/se...
// Свою функцию (которая формирует li - например, она называется createLi) вы будете запускать внутри setInterval:
// setInterval(createLi, 1000);
// Вся разметка должна быть создана джаваскриптом. В HTML в начале body должен быть пустой.

let ul = document.querySelector('ul')
let select = document.querySelector('select');
for (let i = 1; i < 6; i++) {
    let option = document.createElement('option');
    option.innerText = 'Категория ' + i;
    select.appendChild(option);
}

function createLi() {
    let li = document.createElement('li')
    li.innerText = 'Hello'
    ul.appendChild(li)
}
setInterval(createLi, 1000)
