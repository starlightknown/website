---
title: Validate messages/events 
description: In this tutorial, you'll learn how to validate messages/events using AsyncAPI.
weight: 130
---

# Introduction
In this tutorial, you'll learn how to validate messages/events which are sent to your application using AsyncAPI.

# Background Context
A message broker is software that enables applications, systems, and services to communicate with each other and exchange information, in this case messages/events.
You will be using [Eclipse Mosquitto](https://mosquitto.org/) broker. The MQTT protocol provides a lightweight method of carrying out messaging using a publish/subscribe model.
You will be using MQTT client that runs an MQTT library and connects to an MQTT broker over a network. Here publishers and subscribers are MQTT clients. The publisher and subscriber labels refer to whether the client is currently publishing messages or subscribed to receive messages.

In previous tutorial, you have generated your application using [AsyncAPI Generator](https://github.com/asyncapi/generator) Node.js template.
Now you will be validating the messages/events which you will be sending to your application using Mosquitto broker and MQTT client.

#  Validate messages
In this step, we will send a message to our application using MQTT broker and check the error logged if we send an invalid message

1. Start your generated application

<CodeBlock language="bash">
{`npm start`}
</CodeBlock>

2. Send a correct message to your application:

<CodeBlock language="bash">
  {`mqtt pub -t 'light/measured' -h 'test.mosquitto.org' -m '{"id": 1, "lumens": 3, "sentAt": "2017-06-07T12:34:32.000Z"}'`}
  </CodeBlock>

