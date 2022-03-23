# Q1

## Part 1

For question 1.1, I want to you choose a language you are familiar with and write a Dockerfile for it.
Try to do one or two if you can.

Experiment with the containers as I did during the demo.
Create them, start them, stop them, attach to them, exec into them, etc.

## Part 2

Write a docker-compose file to run the images you build in the previous question.

#Q2

I would like you, in the `wordpress` folder, to create a docker-compose file that runs:

1. A wordpress site instance, that persists its data between invocations
2. A mysql database, that persists its data between invocations
3. A phpmyadmin service

All of these containers must be joined to the same network.
