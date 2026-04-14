# IsThisADeal.ai
[IsThisADeal.ai](IsThisADeal.ai) is a solo-built SaaS product I created focusing on blending data science with psychology's cognitive load science.

## The Pain Points
### 1. Cognitive Load

Did you know that the average amount of things someone can hold in their memory is around 4 (Cowen)? Four different things in your head at once, that's the limit. It's why US telephone numbers are split up like they are (333-333-4444).

Now how are you supposed to compare computers, products with a dozen or more variables and components, all at the same time? And what happens when you want to change what you're comparing? Cognitive Bias is what happens when you try to make a decision when overwhelmed, and it leads to dissatisfaction, remorse, returns of products, and discouragement. I know, it happened to me.

### 2. Deals and Sales

Oftentimes you may find a laptop that someone else swears was cheaper before. Was there a past sale? If you are a little more patient, could you save several hundred more dollars? We aim to address that uncertainty - not to mention the 'fake sales' that appear on a concerningly frequent basis.

### 3. Multiple Stores

Say you have researched enough to find out what sort of laptop you like. Now you have to repeat that same search across several websites, trying to find if what you want is in stock... or even exists. (I learned my ideal laptop didn't exist)

### 4. Same laptop, different stores, different prices

One of the annoying things about buying something is that you're never quite certain if someone else has it cheaper. We found a way to address that

### 5. Knowledge

We don't all have time to sit down and educate ourselves over several weeks on the various components that go into computers and what that means for our own life

## The Fixes
* IsThisADeal.ai pulls data from every single major laptop store in the US on a daily basis, taking note of their laptop inventory and prices
* It normalizes the all the laptop data into a clean, **searchable** format. IsThisADeal.ai is now a one-stop-searchable-shop for every laptop
* It builds a custom statistical model tracking components and price relations, so it can accurately predict the average value of a laptop. This is HUGE, because it gives a baseline for what the true 'value' of a computer is, and if the current price is a good deal or not.
* It charts out the price data over time, so a user can easily view the price history and prior sale times
* IsThisADeal.ai also finds the same laptop across multiple retailers, and shows you if there's another store with the same laptop at a lower price. Everything is about transparency
* We wrote a bunch of short, concise, *metric-based* notes about each component to quickly educate the user without falling into the banal corporate 'everything is good' speak. There ARE differences between computers, and that means that some are slower or bad fits. We stripped out the fluff.

There's a lot more, but suffice to say is that I wanted to build something that was user friendly, stayed within a normal human's cognitive capacity, and made life easier and cheaper for us all. We all have enough stresses in life, we can build ways for our current environment to enhance our decision making abilities and not overwhelm us.

## The tech
Without divulging too much of the secret sauce, the concepts are simple.
* We need data, so we use Python to grab it for us, with multiple different approaches (API calls, requests lib, selenium, CDP)
* We need to normalize data, which again is Python's wheelhouse, and uses a long chain of converts (BeautifulSoup, JSON) and logical parsers
* We house the data in a SQL relational database. Since we're working with thousands of rows and not hundreds of thousands, SQLite3 is the most efficient and lightweight option. (When making the schema, remember DRY!)
* We need to process the data to get our helpful insights (and not just overwhelm a user), like prices averages, metrics, and building the statistical model.
* Due to the daily update of the product, we can utilize more in-depth post-processing of the data to create a much quicker caching layer on all our queries.
* Then we host it on a web framwork, using Flask since Python was already integral to all our other backend work. Lots more goes into here like static assets, sitemaps, and all the API code.
* Build a frontend interface using the vanilla languages (HTML, CSS, JS), so we can fully understand the frontend languages and not get abstracted away into JS frameworks. Foundations matter. Understanding matters.
* Host it to Google Cloud Run in a dockerized container

## Conclusion
It's been a really fun project, and something I hope to use my experience with to continue finding ways to make life easier for all of us.
