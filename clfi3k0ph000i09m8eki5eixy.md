---
title: "Ruby gem for Novu Api's"
seoTitle: "Ruby gem for Novu Api's"
seoDescription: "Novu is an open-source notification infrastructure designed to help engineering teams build rich product notification experiences."
datePublished: Tue Mar 21 2023 10:12:25 GMT+0000 (Coordinated Universal Time)
cuid: clfi3k0ph000i09m8eki5eixy
slug: ruby-gem-for-novu-apis
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/GnvurwJsKaY/upload/53fdad1e1e538cc71ed3e59b65ed4c97.jpeg
tags: ruby, ruby-on-rails, notifications, novu

---

### **Introduction** 👋

[Novu is an open-source notification infrastructure designed to help engineering teams build rich product notification experiences without constantly reinventing the wheel](https://novu.co/).

One such library is the Novu client library, which is used for communicating with the Novu API. The Novu API is a powerful tool that allows you to manage notifications and other data in your Novu account.

### **Why Use Novu?** 👀

Developing a notification layer is a common challenge when designing new applications. The process usually starts with sending simple emails, but as the application grows, managing hundreds of notifications across multiple channels becomes cumbersome. Novu's goal is to assist developers in creating meaningful, transactional communication between the product and its users, all while providing an easy-to-use API and outstanding developer experience.

Unified API Today, users receive communication across various providers such as Sendgrid for Email, Twilio for SMS, Mailchimp, Push, Web-Push, and Chat messaging (Slack, etc.). Users expect customization of communication channels to fit their needs and goals. Consequently, developers must manage all of those APIs across the codebase.

Novu solves this challenge by providing a unified API to manage all customer communication. With Novu, developers can add a new provider or switch email providers seamlessly.

### **Installation 🧑🏼‍💻**

To install the Novu client library, you can use RubyGems. Simply run the following command in your terminal:

```ruby
gem install novu
```

Alternatively, you can add the library to your Gemfile and run the `bundle install`.

```ruby
gem 'novu'
```

### Usage **⚡️**

Once you have installed the gem, you can start using it in your Ruby code. The first step is to initialize the client with your API token:

```ruby
require 'novu'
client = Novu::Client.new('MY_API_TOKEN')
```

Replace `MY_API_TOKEN` with your actual API token. You can find your API token from settings by visiting the Api keys option.  
  
`Note: You have to signup on`[`Novu`](https://web.novu.co/)`to get the API key from their dashboard.`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679375227912/a621ff4a-f035-48d8-a4a9-5f0a0d124e78.png align="center")

After initializing the client, you can call methods on it to interact with the Novu API. For example:

* To get a list of notifications, you can use the following code:
    

```ruby
client.notifications
```

This will `return an array of notification objects`. You can also pass parameters to this method to filter the results.

Similarly, to trigger an event you can use the following code:

`The trigger event is the main (and the only) way to send notifications to subscribers. The trigger identifier is used to match the particular template associated with it.`

```ruby
client = Novu::Client.new('MY_API_TOKEN')
 
body = {
  name: '<notification_template_id>',
  payload: {
    customVariables: 'Hello'
  },
  overrides: {
    fcm: {
      color: '#fff'
    }
  },
  to: {
    subscriberId: '<USER_IDENTIFIER>',
    email: 'amansaini0003@gmail.com',
    firstName: 'Aman',
    lastName: 'Saini',
  },
  transactionId: 'transactionId'
}.to_json

# trigger event
client.trigger_event(body)
```

```ruby
# HTTP Status Code: 201
# Response Body:
{
    acknowledged: true,
    status: "status",
    error: ["error"],
    transactionId: "transactionId"
}
```

For more information about the [**available methods**](https://github.com/amansaini0003/ruby-novu/blob/main/README.md) and their parameters, you can refer to the [**Novu API documentation**](https://docs.novu.co/api/overview/).

### **Conclusion 🚀**

Novu is an open-source notification infrastructure designed to assist engineering teams in creating meaningful, transactional communication between the product and its users, all while providing an easy-to-use API and an outstanding developer experience. By using Novu, developers can simplify the management of multiple communication channels and providers, improving efficiency and productivity. By following the installation and usage instructions provided above, you can start using the library in your Ruby projects right away.

Cheers,  
[**Aman Saini**](https://amansaini.netlify.app/)

PS. If you find the article relevant, then please share it with your network. 🙏

**References**

* [Novu API's](https://docs.novu.co/api/overview/)
    
* [Ruby gem for Novu Api](https://rubygems.org/gems/novu)
    
* [Ruby Gem GitHub Repo](https://github.com/amansaini0003/ruby-novu)