# TelTech Sample Project

Welcome to your interview challenge! Here at TelTech we're making leaps and strides to using technologies such as [Docker](http://www.docker.com) and [Service Oriented Architectures](http://en.wikipedia.org/wiki/Service-oriented_architecture) to easily scale our team and products. 

### The Challenge
Using the language of your choice, you'll need to do the following.

1. Connect to a RabbitMQ server, the endpoint will be provided to you.
2. Declare a queue on the Rabbit server
3. Bind the queue to the `amq.topic` exchange
4. Consume messages produced on your queue. Messages will contain the following
    * A simple math formula for you to parse and solve
    * A unique ID to produce a response with the solution embedded
5. Produce a message back onto the queue
    * Exchange should be `amq.topic`
    * Topic should be `formula_solution`
    * Payload should contain the original message with the solution placed in the `solution` field. 
    * See the [example below](#example) to better understand the message format

In order to complete this challenge, your problem must be able to solve at least 60 problems a minute. To solve this problem you will need to be able to translate the formula provided as a string and return an `integer` that represents the solution to the math problem provided. 

The efficiency of the microservices we create here at TelTech really matters and this challenge will help you understand the general idea of how our infrastructure operates and how to link in to create microservices in our real architecture.

### Message Format
Sending and receiving messages will be in the same format as a JSON object. When you receive the JSON object the solution field will be null, and when you reply the solution field ought to be filled out with the appropriate solution.

### <a name="example"></a> Example
The server will send you a message that resembles the JSON object below.
```js
{
    "uuid": "3c4ea4c0-80f4-11e4-b4a9-0800200c9a66",
    "formula": "42 + 5 - 10 - 30 + 2",
    "solution": null
}
```
If you were to receive the message above, the example below is what you're expected to produce as a solution.
```js
{
    "uuid": "3c4ea4c0-80f4-11e4-b4a9-0800200c9a66",
    "formula": "42 + 5 - 10 - 30 + 2",
    "solution": 9
}
```

### Summary
If you have any questions to better understand the solution and discuss possible approaches to solving this challenge, you may feel free to contact the individual you've interviewed with. The last thing we ever intend to do is deeply confuse people and we'll make sure that you have everything you need to get started with solving this challenge. Best of luck!
