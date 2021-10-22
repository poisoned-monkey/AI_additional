# Отчет по дополнительному заданию по курсу "Искуственный интеллект"

[Схема](https://github.com/poisoned-monkey/AI_additional/blob/main/ES_AI.jpg)

# Листинг кода

```
:- dynamic(fact/1).
:- dynamic(nfact/1).
:- dynamic(lang/1).

solve(X) :- repeat, lang(X), retract(lang(X):-_).

lang('C') :- has('r1'),has('r2'),has('r3'),has('q6').
lang('C++') :- has('r1'),has('r2'),has('r3'),has('q6'),has('q1').
lang('C#') :- has('r1'),has('r2'),has('r7'),has('q5'),has('q1'),has('q3'),has('q7'),has('q6').
lang('Java') :- has('r1'),has('r2'),has('r7'),has('q5'),has('q1'),has('q3'),has('q7'),has('q6').
lang('JS') :- has('r1'),has('r6'),has('r5'),has('q5'),has('q1'),has('q3'),has('q7'),has('q4'),has('q2').
lang('Python') :- has('r1'),has('r6'),has('r5'),has('q2'),has('q1'),has('q3'),has('q5'),has('q7'),has('q6').
lang('Prolog') :- has('r4'),has('r6'),has('r5'),has('q2'),has('q3').
lang('Bash') :- has('r3'),has('r5'),has('q1').

has(X) :- fact(X), !.
has(X) :- nfact(X), !, fail.

has('r1') :- write('решение задачи последовательное?'), read(Z),
    assert_fact(Z,'r1').
has('r1') :- write('ручная работа с памятью?'), read(Z),
    assert_fact(Z,'r1').
has('r2') :- write('быстрый исполняемый код?'), read(Z),
    assert_fact(Z,'r2').
has('r2') :- write('часто будете запускать программу?'), read(Z),
    assert_fact(Z,'r2').
has('r3') :- write('есть опыт работы с памятью и архитектурой пк?'), read(Z),
    assert_fact(Z,'r3').
has('r4') :- write('у вас не много опыта в программировании?'), read(Z),
    assert_fact(Z,'r4').
has('r6') :- write('нужна быстрая скорость разработки?'), read(Z),
    assert_fact(Z,'r6').
has('r5') :- write('вы не знаете что такое терминал?'), read(Z),
    assert_fact(Z,'r5').
has('r7') :- has('r3').
has('r7') :- has('r6').

has('q1') :- write('вам нравится ООП код?'), read(Z),
    assert_fact(Z,'q1').
has('q2') :- write('вам нравится писать скрипты?'), read(Z),
    assert_fact(Z,'q2').
has('q3') :- write('вам нужен сборщик мусора?'), read(Z),
    assert_fact(Z,'q3').
has('q4') :- write('ваш стиль кода функциональный?'), read(Z),
    assert_fact(Z,'q4').
has('q5') :- write('вам нужен JIT?'), read(Z),
    assert_fact(Z,'q5').
has('q6') :- write('вам нужна поддержка многопоточности?'), read(Z),
    assert_fact(Z,'q6').
has('q7') :- write('вам нужна разработка на другие платформы?'), read(Z),
    assert_fact(Z,'q7').

assert_fact(yes,X) :- asserta(fact(X)).
assert_fact(no,X) :- asserta(nfact(X)), fail.

```

# Примеры запросов/ответов

решение задачи последовательное?
yes
быстрый исполняемый код?
no
часто будете запускать программу?
no
ручная работа с памятью?
yes
нужна быстрая скорость разработки?
yes
вы не знаете что такое терминал?
yes
вам нужен JIT?
yes
вам нравится ООП код?
yes
вам нужен сборщик мусора?
yes
вам нужна разработка на другие платформы?
yes
ваш стиль кода функциональный? 
no
вам нравится писать скрипты?
yes
вам нужна поддержка многопоточности?
yes
X = 'Python'
решение задачи последовательное?
yes
быстрый исполняемый код?
yes
есть опыт работы с памятью и архитектурой пк?
yes
вам нужна поддержка многопоточности?
yes
X = 'C'
решение задачи последовательное?
no
ручная работа с памятью?
no
у вас не много опыта в программировании?
yes
нужна быстрая скорость разработки?
yes
вы не знаете что такое терминал?
yes
вам нравится писать скрипты?
yes
вам нужен сборщик мусора?
yes
X = 'Prolog'

