### Create a Custom Hasher for Laravel 5 
This code sample will help you to create a custom hashing to replace Laravel's default hash mechanism  .

### How to use the sample

Create a folder "Libs" inside your project's /app folder . Copy the folder "CustomHash" availlable in the repo to newly created "Libs" folder . You can see a class file with name "CustomHasher.php" inside this folder. This is the main logic for custom hashing .
Now copy the "app/Providers/CustomHashServiceProvider.php"  file from the repo to your "app/Providers" folder in your project .
Open your /config/app.php file and check for the following line in your Providers array :

Illuminate\Hashing\HashServiceProvider::class,

Remove  or comment the above line and add following line of code :

App\Providers\CustomHashServiceProvider::class

Now it works from custom hash provider.

### To modify password encode logic 

In the sample repo, check Libs/CustomHash/CustomHasher.php file and see following function :

 public function make($value, array $options = array()) {		
		//I have custom encoding / encryption here//
		//Define your custom hashing logic here//
        return base64_encode(base64_encode($value));
 }
 
 Change this code to implement a custom encoding for passwords .
 
 


