# lab-2-submission

https://youtu.be/gHj8leSTla4


# Links


https://github.com/ObaidaKandakji/store-front-demo


https://github.com/ObaidaKandakji/order-service-demo


https://github.com/ObaidaKandakji/product-service-demo

# README

## What changes did you make to the order-service and product-service to comply with the Configurations and Backing Services factors of the 12-Factor App methodology?  
To follow the 12-Factor principles, we separated each service into its own GitHub repo and made sure all dependencies are properly declared (`package.json` for Node.js and `Cargo.toml` for Rust). We also replaced hard-coded values with environment variables. For example, the order-service now pulls its port and RabbitMQ connection string from a `.env` file using `dotenv`, while the product-service does the same with its port using the `dotenv` crate. This setup means databases and queues are treated as external resources, so we can swap them just by changing environment variables without touching the code.  

## Why is it important to use environment variables instead of hard-coding configurations in your application?  
Using environment variables keeps configuration separate from the code, which makes it easier to run the same app in different environments like development, testing, and production. It also helps keep sensitive information (like passwords or API keys) out of version control, which improves security. Overall, it makes the app more flexible, easier to maintain, and safer to deploy.  

## Why is it important to have separate repositories for each microservice? How does this help maintain independence and scalability of each service?  
Having separate repos lets each microservice evolve on its own, with its own commits, issues, and deployment pipeline. This means teams can work independently without breaking each other’s code and can even choose the best tech stack for each service. It also makes scaling easier because services don’t depend on a single shared repo or release cycle, which keeps everything more modular and manageable.  
