databaseMame:query
collection:car


#Men who own a Pink car
==>db.car.find({gender:"Male",car_color:"Pink"})


#Women who own a Red or a Blue Car
==>db.car.find({$and: [{gender: "Female"},{$or: [{car_color: "Red"},{car_color: "Blue"}]}]})


#Men who purchased the car in the year 1998
==>db.car.find({$and:[{gender:"Male"},{purchase_year:"1998"}]})


#Women who purchased a Yellow car in the year 1985
=>db.car.find({$and:[{gender:"Female"},{car_color:"Yellow"},{purchase_year:"1985"}]})


#Men who either have a Red or Green car and either live in Germany or Kenya
    ==>db.car.find({$and:[{gender:"Male"},{$or:[{car_color:"Red"},{car_color:"Green"}]},{$or:[{country:"Germany"},{country:"Kenya"}]}]})


#People from India who purchased cars in the year 2001
==>db.car.find({$and:[{purchase_year:"2001",{country:"India"}}]})


#People from Germany or Egypt who purchased cars in the year 1998 or 1992
==>db.car.find({$and:[{$or:[{country:"Germany"},{country:"Egypt"}]},{$or:[{purchase_year:"1998"},purchase_year:"1992"]}]})

#Women from India who own a Blue car
==>db.car.find({$and:[{country:"India"},{car_color:"Blue"}]})

#Men from Germany who purchased cars in 1998 and Men from Egypt who purchased cars in 1992
===>db.car.find({$and:[{$and:[{gender:"Male"},{country:"Germany"},{purchase_year:"1998"}]},{$and:[{gender:"Male"},{country:"Germany"},{purchase_year:"1992"}]}]})

#Women who own a Green car and are not from Pakistan
===>db.car.find({$and:[{gender:"Female"},{car_color:"Green"},{country:{$ne:"Pakistan"}}]})