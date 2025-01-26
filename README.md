## Project-Trainning
### Technology is used
1.Php

2.Mysql

3.HTML

4.CSS

5.Javascript

6.Bootstrap

## How to run 

# Install laravel
```sh
composer global require laravel/installer

laravel new myproject
```
# Install laragon
We can search for Laragon online and download it

# Create data tables and sample data
```sh
php artisan migrate
php artisan db:seed 
```
### Function
1.Visitors and users can view the content of store pages and new titles.

2.The site has ordering functions and, if necessary, it is possible to leave a review for the site in the commnet page.

3.When Order and Contact will send a .txt file that will automatically download to your device

4.The dashboard page has the functions of registering, logging in, changing password, and forgetting password

5.We can manage information including the functions of adding, editing, deleting, and searching for content in the food and new tables in the dashboard..

## The API I used

# Change password
```sh
public function reset(Request $request)
    {
        $request->validate([
            'email' => 'required|email',
            'password' => 'required|confirmed|min:8',
            'token' => 'required'
        ]);

        $status = Password::reset(
            $request->only('email', 'password', 'password_confirmation', 'token'),
            function ($user) use ($request) {
                $user->password = Hash::make($request->password);
                $user->save();
                Auth::login($user);
            }
        );

        return $status === Password::PASSWORD_RESET
            ? redirect()->route('login')->with('status', __($status))
            : back()->withErrors(['email' => [__($status)]]);
    }
```
![image](https://github.com/user-attachments/assets/d8ea6e97-a4de-4544-bba9-d7c495c7f35a)

### Page interface
1. Login Page:
     ![image](https://github.com/user-attachments/assets/cf740dc2-b402-4c74-bd94-1804df7f78a7)

2. Register Page: ![image](https://github.com/user-attachments/assets/7848fad3-b642-4e25-966d-914eb7b523d2)

3.Forgot-password Page:  ![image](https://github.com/user-attachments/assets/ba835d65-4628-4b1c-8e5d-cd1f1cd2f5ed)


4. Dashboard Page:
     ![image](https://github.com/user-attachments/assets/75ca0286-9dff-4869-89ed-edfd6882ca31)
    url:http://127.0.0.1:8000/admin
   
5. Change-password :
   ![image](https://github.com/user-attachments/assets/441fe325-1f01-468b-90e2-3d28fccecd1e)

  
6. Food Page:
    ![image](https://github.com/user-attachments/assets/37110e7e-7ca5-4569-be3f-dccd79296650)
    url:http://127.0.0.1:8000/store
   
7. New title Page: ![image](https://github.com/user-attachments/assets/a8addbb7-5cf1-4873-84a4-1d34ef207de6)

8. Contact Page: ![image](https://github.com/user-attachments/assets/03f599c7-879f-428c-9c4f-c8f80a8ffca8)

9. Order Page: ![image](https://github.com/user-attachments/assets/fd64257b-f1c8-4f35-8b1c-94b9d088ab0e)

10. Comment Page: ![image](https://github.com/user-attachments/assets/66117e4b-33dc-4faf-8a4c-e933169b317a)




    
