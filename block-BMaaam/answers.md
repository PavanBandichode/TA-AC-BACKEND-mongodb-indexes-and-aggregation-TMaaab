1. db.data.aggrigate([{$match :{isActive:true}}]).pretty();

2. db.data.aggrigate([{$match :{gender:"male"}},{$match :{$inc :{name :"Blake"}}}]).pretty();

3. db.data.aggregate([{$match: {gender: "male"}}]).pretty();

4. db.data.aggregate([{$match: {gender: "male"}}, {$match: {isActive: true}}]).pretty()

5. db.data.aggregate([{$match: {gender: "male"}}, {$match: {isActive: true}},{$match :{age:{$gte :25}}}]).pretty()

6. db.data.aggregate([{$match: {gender: "male"}}, {$match :{age:{$gt :40}}},{$match :{eyecolor:"blue"}}]).pretty()

7. db.data.aggregate([{$match: {"company.location.country": "USA"}}, {$match: {eyeColor: "blue"}}])

8. db.data.aggregate([{$match: {gender: "female"}},{$match: {"company.location.country": "Germany"}}, {$match: {eyeColor: "green"}}, {$match: {favoriteFruit: "apple"}}])

9. db.data.aggrigate({
   $group:{
        _id: "$gender",
   count: { $sum: 1 },
   }
   })

10. db.data.aggregate([{$match: {eyeColor: "green"}}, {$group: {
    _id: null,
    count: {$sum: 1}
    }}])

11. db.data.aggregate([{$match: {gender: "female"}},{$match: {eyeColor: "brown"}}, {$group: {
    _id: null,
    count: {$sum: 1}
    }}])

12. db.data.aggregate([{$group: {
    _id: "$eyeColor",
    count: {$sum: 1},
    }}])

13. db.data.aggregate([{$match: {gender: "female"}},{$match: {$inc: {tags :"amet"}}}, {$group: {
    _id: null,
    count: {$sum: 1}
    }}])

14. db.data.aggregate([{
    $group:{
    _id: null,
    avg_age: {$avg: $age}
    }
    }])

15. db.users.aggregate([
    {
    $group: {
    _id: "$gender",
    avg_age: { $avg: "$age" },
    },
    },
    ]);

16. db.collection.aggregate({
    $group : { 
        _id: null, 
        max: { $max : "$age" }
    }});

17. db.collection.aggregate({
    $group : { 
        _id: null, 
        max: { $min : "$age" }
    }});

18. db.data.aggregate([{$group: {
    _id: null,
    sum_age: {$sum: "$age"}
    }}])

19. db.data.aggregate([{$match: {gender: "male"}},{$group: {
    _id: "$eyeColor",
    count: {$sum: 1}
    }}])

20. db.data.aggregate([{$match: {gender: "female"}},{$match :{age :{$gt :30}}},{$group: {
    _id: "$age",
    count: {$sum: 1}
    }}])

21. db.data.aggregate([{$match: {gender: "male"}}, {$match: {eyeColor: "blue"}}, {$match: {"company.location.country": "Germany"}}, {$group: {
    _id: null,
    men_in_germany: {$sum: 1}
    }}])

22. db.data.aggregate([{$unwind: "$tags"}, {$group: {
    _id: "$tags",
    count: {$sum: 1}
    }}])

23. db.data.aggregate([{$match: {favoriteFruit: "banana"}}])
