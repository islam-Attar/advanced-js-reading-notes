# Reading: Application State with Redux

State management is one of the most important topics in modern web applications.

Redux is a state management library that allows you to manage app level state and gives you the ability to elevate your applications as well as improving your general understanding of building JavaScript UIs.

### Why use Redux?

As you already know, questions like “Why should you use A over B?” boil down to your personal preferences.

I have built apps in production that don’t use Redux. I’m sure that many have done the same.

For me, I was worried about introducing an extra layer of complexity for my team members. In case you’re wondering, I don’t regret the decision at all.

Redux’s author, Dan Abamov, also warns about the danger of introducing Redux too early into your application. You may not like Redux, and that is fair enough. I have friends who don’t.

That being said, there are still some very decent reasons to learn Redux.

For example, in larger apps with a lot of moving pieces, state management becomes a huge concern. Redux ticks that off quite well without performance concerns or trading off testability.

One other reason a lot of developers love Redux is the developer experience that comes with it. A lot of other tools have begun to do similar things, but big credits to Redux.

Some of the nice things you get with using Redux include logging, hot reloading, time travel, universal apps, record and replay — all without doing so much on your end as the developer. These things will likely sound fancy until you use them and see for yourself.

Dan’s talk called Hot Reloading with Time Travel will give you a good sense of how these work.

Also, Mark Ericsson, one of Redux’s maintainers, says that over 60% of React apps in production use Redux. That’s a lot!

Consequently, and this is just my thought, a lot of engineers like to show potential employers that they can maintain larger production codebases built in React and Redux, so they learn Redux.

If you want some more reasons to use Redux, Dan, the Redux creator, has a few more reasons highlighted in his article on Medium.

If you don’t consider yourself a senior engineer, I advise you to learn Redux — largely because of some of the principles it teaches. You’ll learn new ways of doing common things, and this will likely make you a better engineer.

Everyone has different reasons for picking up different technologies. In the end, the call is yours. But it definitely doesn’t hurt to add Redux to your skill set.

In simple terms, with Redux, it is is advisable to store your application state in a single object managed by the Redux store. It’s like having one vaultas opposed to littering money everywhere along the bank hall.

If you want to update the state of your application, you convey your action to the reducer.

Redux is simply a store to store the state of the variables in your app. Redux creates a process and procedures to interact with the store so that components will not just update or read the store randomly. Similar to the bank. It does not mean because you have money in the bank that you can go anytime, open the vault, and take money. You have to go through certain steps to withdrawal money.

In short, Redux is a way to manage the “state” or we can say it is a cache or storage that can be accessed by all components with a structured way. It has to be accessed through a “Reducer” and “Actions”

![redux](./assets/redux.png)

# When to use Redux

Lately one of the biggest debates in the frontend world has been about Redux. Not long after its release, Redux became one of the hottest topics of discussion. Many favored it while others pointed out issues.

Redux allows you to manage your app’s state in a single place and keep changes in your app more predictable and traceable. It makes it easier to reason about changes occurring in your app. But all of these benefits come with tradeoffs and constraints. One might feel it adds up boilerplate code, making simple things a little overwhelming; but that depends upon the architecture decisions.

One simple answer to this question is you will realize for yourself when you need Redux. If you’re still confused as to whether you need it, you don’t. This usually happens when your app grows to the scale where managing app state becomes a hassle; and you start looking out for making it easy and simple.
