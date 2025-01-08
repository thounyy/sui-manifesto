# A Manifesto for Remarkable Sui Codebases

> A living document for Sui developers committed to code excellence

## Purpose
This manifesto represents our collective commitment to raising the standards of development in the Sui ecosystem. It's designed to evolve with our community's insights and experiences.

## Contributing
We welcome contributions from all Sui developers. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

The Sui ecosystem has reached a turning point. With mature tooling, robust infrastructure, and growing adoption, we now face a different challenge: the quality of what we build. As the barriers to entry lower and development accelerates, we must raise our standards.

This isn't just about writing code that works - it's about crafting code that endures, that compounds, that elevates our entire ecosystem. The immutable nature of blockchain demands excellence, and Sui's unique capabilities enable it. We can no longer accept shortcuts or compromise on quality.

With Move 2024 and the Sui Developer Roadmap, Mysten engineers have given us the foundation we need. Now it's our turn. This manifesto is a call to action for every Sui developer to embrace higher standards, to build with purpose, and to contribute to a legacy of excellence.


## The Art of Eternal Code

Code deployed on chain lives forever - or at least until validators run out of incentives. This permanence demands impeccable standards. Moreover, programming on Sui represents an entirely new paradigm, one that answers to new principles and responsibilities.

### Code that Speaks

When we write code, we must remember that it rarely serves us alone. Contributors will study our code to improve it or adapt it to their needs. Developers will integrate our codebase into their projects. Beginners will learn from our examples, studying and reproducing our patterns. This reality demands that we prioritize readability above all else. Let's resist unnecessary optimization - clear intent over cleverness.

Move Conventions provide essential best practices for writing Move smart contracts on Sui. While these conventions aren't strict rules, they represent a tacit agreement among Sui developers, ensuring consistency across our ecosystem and making code both easier to understand and maintain.

### Built to Last

The Conventions also showcase critical patterns that demand our attention. One of the most representative cases, intrinsically tied to Sui's architecture, is the gas storage fund. Computing and storing data on Sui costs gas, with storage gas being refunded upon data deletion. Our code must account for this reality, providing functions for a complete lifecycle of the different objects.

Upgrade policies on Sui require special consideration due to the immutable nature of packages. We must design our codebase with long-term upgrade strategies in mind. This means achieving separation of concerns but also taking into account the upgrade frequency of the different packages. Code that is supposedly never upgraded shouldn't share a package with code requiring regular feature updates. Objects depending on specific package versions must be properly versioned. Users deserve absolute clarity about which version of code they're executing, and when and how upgrades occur.

The management of packages via Cap objects demands our careful attention. As Sui developers, we often define different types of Cap with multiple instances of each. This can quickly become messy and unsafe without rigorous methodology. Caps must remain secure yet accessible - a balance we must constantly maintain.

### Truth in Testing

Testing isn't just a safety net - it's the foundation of fearless development. When we write tests, we're not just catching bugs; we're documenting our intentions, designing better interfaces, and building confidence in our code. Each test tells a story about how our software should behave, serving as both a guardian against regressions and a guide for future developers.

As a general best practice, we must separate unit tests from the rest of the code. Test functions located at the end of modules should serve only as helpers for the actual tests in the tests directory. This approach verifies that code exposes objects and functions only in intended ways - you can't use a private function in a separate test module, but you can in a test within the same module. To accelerate writing, the Builder pattern proves invaluable, where needed objects are instantiated and held in a hot potato upon test start and deleted at once at the end.

While audits provide value, they aren't bulletproof. We must not rely exclusively on external auditors but rather on ourselves and the developer community to review and improve our code.

## Code that Compounds

The beautiful thing about code is that it gathers people around a common goal: building the most efficient virtual machinery. Blockchains go one step further by uniting all these machineries into a gigantic but coherent ecosystem.

### The Power of Parts 

Sui is an entirely new Web3 tech stack which brought the object-centric model as opposed to the usual account-based model. Using objects and Programmable Transaction Blocks (PTBs), smart contracts are more composable than ever. This is one of the most powerful features of smart contract platforms - we must harness it fully.

Our designs must revolve around objects that allow app states to be decentralized and assets to be truly owned. At the same time, developers can easily translate their ideas into code as objects have "blockchain physics" built-in. This allows us to create modular architectures that behave like mechanical systems, where parts can be assembled and evolve into something powerful.

### Future-Proof by Design 

Beyond maximizing composability, the structure of our code must remain open whenever possible, welcoming external developers to extend it. This extension can happen through repository forks, but more importantly through direct package integration to develop additional functionality.

When designing our systems, we must think beyond immediate requirements. Our architectures should provide clear extension points, well-defined interfaces, and flexible integration patterns. Think of our code as a living system that will grow and evolve with the ecosystem.

### Building Blocks 

On-chain packages are the building blocks of Sui. Anyone can plug-in or build on top of code living on-chain. We can accelerate the expansion of our ecosystem by compounding our efforts, reusing the existing rather than reinventing the wheel each time. This is how we catch up with well-established ecosystems.

Currently, only two packages - on-chain frameworks - are widely used by our developer community: 0x1 and 0x2. Mysten Labs should not be the only builder of reusable foundations. In a decentralized environment like blockchain, it is our duty to develop the standards and frameworks we need to align our efforts and reach escape velocity.

## Bridging the Gap

Move code is only half the work. Because of the programming model, well-written Move code is barely usable as is. Well-designed SDKs abstracting the complexity of composing PTBs with functions and querying usable data from objects are essential.

### Beyond Smart Contracts 

If on-chain packages are the building blocks of Sui, SDKs are the cement. SDKs are more than simple wrappers around move functions and object ids. They are the link between the Web developer and the on-chain code, facilitating onboarding and usage of the smart contracts. Even more than unit tests, a good SDK clarifies the architecture and features of the packages.

People use them to learn as much as to build with them. By not putting the effort into writing a quality SDK, we basically close the door to most of the developers who would be willing to use our library or protocol - an opportunity that should be honored.

### Knowledge is Power 

The final layer is not written in a programming language - let's talk about documentation. This is the bridge between code and comprehension, transforming complex systems into accessible knowledge. Good documentation comprises four essential types: tutorials, how-to guides, technical reference, and explanation.

- tutorials are made for beginners, with lessons split into series of steps to complete a project.
- how-to guides or cookbooks contain recipes to achieve specific ends, focused on advanced topics. 
- references describe the different parts of the code and how to use them.
- explanations or discussions are made to clarify particular topics.

Documentation is the second door to the product, made for developers but not only. Such material is a net positive for the whole ecosystem and becomes increasingly necessary as the product gains traction.

### Tools of the Trade 

This is a crucial point as our ecosystem is new and some argue that developer tools are lacking. Shipping the tooling we need to build better and faster is as much our responsibility as Mysten Labs'. Many developers have built fantastic CLIs, libraries, apps and more, yet aren't recognized enough. It is our duty to contribute to these codebases by creating issues or directly opening PRs, and even easier, by communicating about them.

## The Community Canvas

A blockchain is only as strong as its community of builders. While technical excellence forms our foundation, it's our collective actions and shared values that truly define our ecosystem. 

### Open by Default

Open-source isn't just a development model - it's the embodiment of Web3's core values of transparency, collaboration, and collective innovation. In a space where we're building the future of digital trust, closed systems contradict our fundamental principles. Open-source code invites peer review, accelerates innovation through shared knowledge, and creates a compounding effect where each builder's contribution strengthens the entire ecosystem.

Code living on chain is de facto open-source because of the Move bytecode which is more easily readable than regular bytecode. Tools like the Revela decompiler or SuiGPT make this really easy. So there is no point in hiding our code!

### Better Together

We are all building a new internet on Sui, together. Our builders excel in collaborative initiatives so let's keep this going. We're starting to see projects come together on technical products, but it would be great to see more as we can learn so much by working together.

Another amazing way to learn, share and gather feedback is to build in public. This means doing live coding sessions, regular spaces, lots of posts to explain new iterations in a product or technical challenges. This engagement also helps grow a supportive community around the project.

Finally, there's a sensitive subject to mention - grifters. As contributors in this ecosystem, it is our responsibility to expose all sorts of frauds. The good news is that this is facilitated by the transparent nature of the blockchain, so let's protect each other against malicious actors.

### Rising Tide

Contributing to Sui is not just writing code, it's growing the pie by all means. As proficient Move developers, let's help beginners with educational content and on development-focused groups. During these years we have learned so much about Web3 and Sui in particular, and yet there is still little material available. Let's share our knowledge and advocate for Sui. We, as technical users, are the most legitimate to speak loudly on socials. Building an open and decentralized internet is a community effort!

---

In the end the most advanced Sui codebase is Sui itself - this is a good example to follow.

These are my personal views based on my 2.5 years experience building on Sui and the last 9 months building account.tech, but I would be happy to update this document to include recommendations from more builders within the ecosystem.

Let's build something remarkable.