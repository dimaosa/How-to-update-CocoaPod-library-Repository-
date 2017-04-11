
# How to update CocoaPod library (repository) step-by-step guide.

<b> 1. Skip this step if you have CocoaPods if not, please install </b>

```ruby
gem install cocoapods
```

<b> 2. Clone code from GitHub to your computer </b> 

```ruby
git clone https://github.com/StarcutFinland/StarFlight
```

<b> 3. Add changes to code and commit them to repository </b>

```ruby
git add .
git commit -m “your changes description”
git push
```

<b> 4. This step indicates that you are marking this commit as a specific release of your pod. The name of the tag should match s.version in your .podspec file. </b>

The next step will validate this.

```ruby
git tag NEW_VERSION_NUMBER
git push origin NEW_VERSION_NUMBER
```

<b>5. Next step is to update Podspec (COCOAPOD_NAME.podspec) which located in the root </b>

![alt tag](https://github.com/dimaosa/How-to-update-CocoaPod-library-Repository-/blob/master/Images/podSpecScreenShot.png)

<b> 6. Now, validate Podspec by command </b>

```ruby
 pod spec lint COCOAPOD_NAME.podspec
 ```
> Output Should look like:
  
```ruby
>   My-MacBook-Pro:PROJECT_FOLDER dima.osadchy$ pod spec lint COCOAPOD_NAME.podspec 
> 
> 	 -> COCOAPOD_NAME (0.1.3)
> 
> 	Analyzed 1 podspec.
> 
> 	StarFlight.podspec passed validation.
```

<b> 7. Commit changes if step 5 validate </b>

```ruby
git add .
git commit -m “Update Version number to <NEW_VERSION_NUMBER >”
git push
```

<b> 8. And the last step is to update CocoaPod </b> 

```ruby
pod trunk push NEW_VERSION_NUMBER.podspec
```

If <b> Step 8 failed </b> with error  <b> You need to register a session first </b>.
Register yourself in a trunk:

```ruby
pod trunk register yourEmai@starcut.com 'Name Surname' --description='MacBook Pro'
```
