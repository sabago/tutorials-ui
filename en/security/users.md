#####In this section

In this section you'll learn how to sign-up and log in a User (we call it CloudUser) and let CloudBoost do all the heavy-lifting like session management for your apps. Finally, you will also learn about default properties in CloudUser and how to save or delete a user. 

#Before we begin

CloudUser is inherited from CloudObject class, which means everything that CloudObject contains is also contained in CloudUser and that includes default properties like Id, createdAt, updatedAt, etc. and all of the fucntions like save, delete etc. 

#Sign up.

To sign up a new user you need to initialize a new variable with the type CloudUser, assign it username and password and call the sign-up fucntion. 

==JavaScript==
```
var user = new CB.CloudUser();
user.set('username','my_username');
user.set('password', 'my_solid_password');
user.set('email', 'email@sample.com');
user.signUp({
  success: function(user) {
  	//Registration successfull
  },
  error: function(error) {
  	//Error in user registration.
  }
});
```

==NodeJS==
```
//Sign up function will not work on NodeJS. If you want to create a new user on the server. You can use save() function of CloudUser instead. 
```

After the CloudUser is signed-up a new session is automatically created for you and the user is logged-in unless you call log-out function of CloudUser object. 

#Default Properties

Every CloudUser when created has default properties attached to it. Here is alist of all the default properties attached to CloudUser when you initialize them. 

* **All of the CloudObject default properties are available in CloudUser, as CloudUser is inherited from CloudObjects. To see what default properties are available in CloudObject, Please click [here]()**

* **Username** : [Text] A unique username of a CloudUser

==JavaScript==
```
console.log(user.username);
```

==NodeJS==
```
console.log(user.username);
```

* **Password** : [Encrypted Text] Password of the ClousUser Object

==JavaScript==
```
console.log(user.password);
```

==NodeJS==
```
console.log(user.password);
```

* **Email** : [Email] An email of the CloudUser object

==JavaScript==
```
console.log(user.email);
```

==NodeJS==
```
console.log(user.email);
```


#Log in

To login a CloudUser you can set the username and password and call the login fucntion / method. 

==JavaScript==
```
var user = new CB.CloudUser();
user.set('username', 'my_username');
user.set('password', 'my_solid_password');
user.logIn({
  success: function(user) {
  	//Login successfull
  },
  error: function(error) {
  	//Error.
  }
});
```

==NodeJS==
```
var user = new CB.CloudUser();
user.set('username', 'my_username');
user.set('password', 'my_solid_password');
user.logIn({
  success: function(user) {
  	//Login successfull
  },
  error: function(error) {
  	//Error.
  }
});
```

Once the user us login you can access the current logged in user by 

==JavaScript==
```
CB.CloudUser.current
```

==NodeJS==
```
CB.CloudUser.current
```

#Log out

If you want to flush the sesison out and log out the user, then you can do this by

==JavaScript==
```
CB.CloudUser.current.logOut({
	success : function(user){
    	//user logged out.
    }, error : function(error){
    	//error
    }
});
```

==NodeJS==
```
CB.CloudUser.current.logOut({
	success : function(user){
    	//user logged out.
    }, error : function(error){
    	//error
    }
});
```

#####What's next?

In the next section you'll learn what roles are, how to add users to roles and security of data on CloudBoost.


