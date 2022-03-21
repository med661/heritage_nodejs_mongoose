# heritage_nodejs_mongoose
the user heritage of the Provider ,
the collection item is the name of collection on mongodb
itemtype: it's the collection that inherits (in that case it's the Provider)
 (see the user.txt "baseOption")
on the Provider collection  :
1)import userShema  (on that case import userModel)
2)add the attributes of the providerShema
3) add : userModel.discriminator('Provider',ProviderSchema) before export the model 
4)then export your model: module.exports = mongoose.model('Provider');
