# Composer quiz package to be used in session

A simple composer quiz package that allows the creation of questions, alternatives and choice of answers in a very easy way.

## Install
```bash
composer require soufraz/quiz-in-session master
```


## Usage

Creating quiz
```
$data = [
    'title' => 'The first quiz of all'
];

$quiz = new Quiz();
$quiz->create($data);
```

Hey: All of the following examples we will assume that **$quiz** is already defined

Adding questions to created quiz
```
$data = [
    [
        'id' => 10,
        'title' => 'How many continents are there on earth?'
    ],
    [
        'id' => 20,
        'title' => 'When was php released?'
    ],
    [
        'id' => 30,
        'title' => 'Bill Gates really stolen a Steve Jobs idea?'
    ]
];

$quiz->addQuestions($data);
```

Adding alternatives to created questions
```
// Mocking a question
$data = [
    'question_id' => 10,
    'alternatives' => [
        'five',
        'six',
        'seven',
    ]
];

$quiz->addAlternativesToQuestion($data['question_id'], $data);
```

LET'S PLAY!

Getting quiz
```
$your_quiz = $quiz->get();
```

Requesting next question and alternatives
```
$question = $quiz->nextQuestion();
```
Hey: If **$question** returns false then quiz is over

Saving answer
```
$quiz->setAnswerToQuestion($question, 2);
```

Getting answers to save ind database or do wherever you want
```
$answers = $this->getQuestions();
```

### Used resources
Boilerplate composer package
https://github.com/stilliard/composer-package-boilerplate

ScallioXTX 
https://www.sitepoint.com/community/t/phpunit-testing-cookies-and-sessions/36557

### License

This project is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)

