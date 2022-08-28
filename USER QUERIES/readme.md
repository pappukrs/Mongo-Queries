Collection - user


#Find all the female users
==>db.user.find({gender:"Female"})
#Find all the female users who speak one of the two languages Kannada, Hindi
==>db.user.find({$and:[{gender:"Female"},{$or:[{language:"Kannada"},{language:"Hindi"}]}]})


#Find all the male users who can speak Hindi and female users who can speak Kannada
===>db.user.find({$or: [{$and: [{gender: "Male"},{language: "Hindi"}]},{$and: [{gender: "Female"},{language: "Kannada"}]}]})

#Find all the users who wear the shirt size S
===>db.user.find({shirt_size:"S"})

#Find all the female users who wear the shirt size XL
===>db.user.find({$and:[{gender:"Female"},{shirt_size:"XL"}]})


#Find all the English speaking male users and Hindi speaking female users
===>db.user.find({$or:[{$and:[{gender:"Male"},{language:"English"}]},{$and:[{gender:"Female"},{language:"Hindi"}]}]})

#Find all the male users who can speak Hindi or English and female users who can speak Kannada or German
===>db.user.find({$or:[{$and:[{gender:"Male"},{$or:[{language:"Hindi},{language:"English"}]}]},{$and:[{gender:"Female"},{$or:[{language:"Kannada},{language:"German"}]}]}]})

#Find all the female users who can speak Bengali who wear shirt size XL and male users who speak German and wear shirt size either L or M

==>db.user.find({$or: [{$and: [{gender: "Male"}, {language: "German"},{$or: [{shirt_size: "L"}, {shirt_size: "M"}]}]},{$and: [{gender: "Female"}, {language: "Bengali"}, {shirt_size: "XL"}]}]})




#Find all the female users who speak any of the Indian languages (Hindi, Punjabi, Bengali, Gujarati, Tamil, Malayalam)
===>db.users.find({$and: [{gender: "Female"}, {language: {$in: ["Hindi", "Punjabi", "Bengali", "Gujarati", "Tamil", "Malayalam"]}}]})


#Men who can speak Korean
===>db.users.find({$and: [{gender: "Male"}, {language: "Korean"}]})
