# Homework-3
```js
//Создаём объект юзера через prompt
function userInfo() {
  var userObj = {};
  do {
    userObj.first_name = prompt("User first_name");
    userObj.last_name = prompt("User last_name");
    userObj.birthday = prompt("User birthday", "2019-11-21")
  } while (userObj.first_name.trim().length < 3 || userObj.last_name.trim().length < 3)
  return userObj
}

var iter = parseInt(prompt("Сколько users добавить ?"));
var users = [{
    first_name: "Josephine",
    last_name: "Robinson",
    birthday: "1996-09-26",
  },
  {
    first_name: "Dean",
    last_name: "long",
    birthday: "1984-10-23",
  },
  {
    first_name: "Sonia",
    last_name: "Holmes",
    birthday: "1958-06-21",
  },
  {
    first_name: "June",
    last_name: "Mcdonalid",
    birthday: "1960-05-06",
  },
  {
    first_name: "ella",
    last_name: "Lane",
    birthday: "1991-12-11",
  },
  {
    first_name: "Felecia",
    last_name: "Stone",
    birthday: "1958-04-21",
  },
  {
    first_name: "Elmer",
    last_name: "George",
    birthday: "1987-12-10",
  },
];


//добовляем юзеров в существующий массив
for (var i = 0; i < iter; i++) {
  users.push(userInfo());
}

console.log(users)

//Делаем большой первую букву в first_name и last_name
function bigFirstLetter(str) {
  return str[0].toUpperCase() + str.slice(1)
}

for (var i = 0; i < users.length; i++) {
  users[i].first_name = bigFirstLetter(users[i].first_name);
  users[i].last_name = bigFirstLetter(users[i].last_name);
}

//Сортируем юзеров по букве Е
var userE = users.filter(function(sort) {
  return sort.first_name.charAt(0) == "E" || sort.last_name.charAt(0) == "E";
});
console.log(userE);

//выбераем юзеров за 30 и сортируем их
var userOld = users.filter(function(user) {
  var old = new Date().getTime() - new Date(user.birthday).getTime();
  return old > 30 * 365 * 86400 * 1000;
})

userOld.sort(function(o, y) {
  var oldMen = new Date(o.birthday);
  var youngMen = new Date(y.birthday)
  return oldMen - youngMen
})
console.log(userOld);
```
