

#Count of Men in Engineering
===>db.employee.find({$and:[{gender:"Male"},{department:"Engineering"}]}).count()


#Count of Women in Engineering who earn less than one million
===>db.employee.find({$and:[{gender:"Female"},{department:"Engineering"},{salary:{$lt:1000000}}]}).count()




#Count of people make less than 80k
===>db.employee.find({salary:{$lt:80000}}).count()


#People who belong Accounting and Legal who make less than 100k
===>db.employee.find()


#Top 10 earning Men
===>db.employee.find().sort({salary:-1}).limit(10)



#Bottom 10 earning Women
===>db.employee.find().sort({salary:1}).limit(10)



#Top 5 earning Engineering people
===>db.employee.find({dapartment:"Engineering"}).sort(salary:-1).limit(5)


#Bottom 5 earning Legal people
===>db.employee.find({department: "Legal"}).sort({salary: 1}).limit(5)



#Women ranked 30 to 50 in terms of salary earned
===>db.employee.find({gender: "Female"}).sort({salary: -1}).limit(20).skip(30)



#Men ranked 50 to 100 in terms of salary earned
===>db.employee.find({gender: "Male"}).sort({salary: -1}).limit(50).skip(50)


#Bottom 50 earning women in Engineering
===>db.employee.find({$and: [{department: "Engineering"},{gender: "Female"}]}).sort({salary: 1}).limit(50)


#Top 50 earning men in Human Resources
===>db.employee.find({$and: [{department: "Human Resources"},{gender: "Male"}]}).sort({salary: -1}).limit(50)

