# Mongoose Discriminators for Data Modeling
Mongoose discriminators are a smart way to organize your MongoDB data. Imagine you have a 'User' model with basic info like name, email, and password. 
Now, say you want to add 'Providers' with additional details like a company name. Instead of creating a whole new model and collection, you can use discriminators.
You define a 'ProviderSchema' with the extra 'company' field and tell Mongoose to make a 'Provider' sub-model of 'User.' This means all your data stays in one collection,
but you can still tell who's a user and who's a provider. It's efficient, keeps your data neat, and makes your life easier when working with MongoDB.
Discriminators help you preserve your data's heritage without complications.
Let's start
the collection item is the name of collection on mongodb

itemtype: it's the collection that inherits (in that case it's the Provider)

(see the user.txt "baseOption");
 
on the Provider collection  

Step 1: Import the User Schema
const userModel = require('./UserModel');
Step 2: Add Attributes for the Provider Schema
const ProviderSchema = new mongoose.Schema({
    company: {
        type: String,
        required: true,
        trim: true,
    },
    // Add other attributes specific to providers here
})

Step 3: Set Up the Discriminator
// Create the 'Provider' sub-model
const Provider = userModel.discriminator('Provider', ProviderSchema);

Step 4: Export the Provider Model
module.exports = Provider;



;
