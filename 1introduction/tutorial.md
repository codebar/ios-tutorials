# Codebar

## iOS Clicker Worksheet

This tutorial is an intro to the world of iOS development, and will help you build your first iOS app.

We'll be building a counter app, where the user will press a button and increment the number on the screen.

### Pre-requisites

In order to do iOS development, you will need a Mac.

Download and install Xcode from the App Store. This may take a while — its a big program.

### Creating a Project

1. Open Xcode and click **Create a new Xcode project**.

  ![step1](./assets/step1.png)

2. Select Single View Application from the **iOS > Application list**, and click **Next**

  ![step2](./assets/step2.png)

3. Fill in the project details:

  * Product Name: Clicker
  * Team: None
  * Organization Name: Whatever you want — your name is always a good fill-in
  * Organization Identifier: com.(OrganizationName)

  Make sure Swift is selected as the language, and Devices is set to Universal.

  Untick the 3 boxes at the bottom.

  Click Next

  ![step3](./assets/step3.png)

4. Select a sensible place to save your project, then hit **Create**.

  Take some time to look around the project that's been created with your coach. What files are there? How do you run your app?

### Build a Button

1. Open up the **Navigation Area** in Xcode, and open up the `Main.storyboard` file.

  > A storyboard is a visual representation of the user interface of an iOS application. It's one of the ways we can create our user interface (the visual bit of an app).

  ![step4](./assets/step4.gif)

2. Now, open the **Utility Area**, and go to the **Object Library**. In the search box, find a button, and drag it to the bottom of the view shown in the storyboard.

  ![step5](./assets/step5.gif)

3. Run you app on the iPhone 7 Plus Simulator. See your button, there in all it's glory at the bottom of the screen. Go ahead - press it!

  Celebrate appropriately.

4. However, it would be even more awesome if our button actually did something.

  To do this we're going to need more than just our storyboard - we'll need a **View Controller**.

  > View controllers are the foundation of your app’s internal structure. Every app has at least one view controller, and most apps have several. Each view controller manages a portion of your app’s user interface as well as the interactions between that interface and the underlying data.

  Think of the view as the puppet, and the view controller as the puppet master. Without something pulling the strings, the view is just a lifeless doll. And without the puppet, the puppet master is just someone doing silly voices to empty air.

  ![muppets gif](https://giphy.com/gifs/frog-muppets-funny-J0UgtZkOjXOe)

5.  Open the `ViewController.swift` file in the **Assistant Editor**. If it's not automatically there when you open the **Assistant Editor**, select it from the automatic or manual routes in the file navigator.

  ![step6](./assets/step6.gif)

6. Let's take a quick look at the code in `ViewController.swift`

  At the top there's some general information on the file and copyright. This is added in every new file you create in Xcode, and you can ignore it.

  Next we import UIKit into this file. UIKit is a framework provided by Apple to help you build iOS apps. It defines the core components - such as `UIButton` (like the one we've added to our storyboard) and `UIViewControllers`, which we're about to use.

  Now onto the interesting bit. This code is creating a new **View Controller** - imaginatively called `ViewController`, and declared it as a type of `UIViewController` - which means it inherits all the useful things a view controller can do.

  There's also 2 functions inside the `ViewController` - `viewDidLoad()` and `didReceiveMemoryWarning()`. We don't actually need these right now, so go ahead and delete them.

  Now our `ViewController` should look like this:


  ```swift
  import UIKit

  class ViewController: UIViewController {


  }```

7. Hold down the **ctrl** button on your keyboard, then click and drag from the button in your storyboard into the `ViewController` code - on an empty line between the `{  ... }`

  In the pop-up that appears:
  * Set the **Connection Type** to be `Action`
  * Type the **Name** of the function as `buttonTapped`

  Hit **Connect**

  ![step7](./assets/step7.gif)

  This has created an `IBAction` - which is an function in our code that is triggered by an action in our storyboard.

8. Let's see if our button works!

  First, in the body of the `buttonTapped` function let's add a print statement:

  ```swift
  @IBAction func buttonTapped(_ sender: Any) {
      print("Hello, world")
  }
  ```

9. Run your app in the iPhone 7 Plus simulator again, and tap on the button.

  ![step8](./assets/step8.gif)

  You should see your message appear in the console!

  /giphy Celebrate

### Count the Clicker

10. Time to build our clicker.

  As you did with the button, find a `Label` from the `Object Library` and drag it onto the storyboard, in the middle of the view.

  (Check back to Step 2 of the last section for a reminder of how to do this)

11. The text of the label is a little small. Head over to **Attributes Inspector** in the **Utility Area** (right hand pane).

  ![step8](./assets/step8.png)

  Increase the font size to 100pt. The original size of the label is now laughably small for our epic font size, so now drag the corners to make it big enough.

  ![step9](./assets/step9.gif)

12. Set the text alignment of your label to be `Centered` - it's in the same place as you set the font size.

13. Now, let's create a link between our label and the `ViewController`.

  We do this using an `IBOutlet`, and it's created the same way as the `IBAction` we used to link our button to the `ViewController`.

  Give it a try - look back at Step 7 if you need to.

  When the popup appears:
    * Set the **Connection Type** to `Outlet`
    * Give it the name `counterLabel`

  Your `ViewController` should now look like this:

  ```swift
    import UIKit

    class ViewController: UIViewController {

      @IBOutlet weak var counterLabel: UILabel!

      @IBAction func buttonTapped(_ sender: Any) {
        print("Hello, world")
      }

    }
  ```

14. Next we want to get actions on our button changing the appearance of our label.

  Inside of your `buttonTapped` function add the following line:

  `counterLabel.text = "🙌"`

  (Hint: To bring up the emoji keyboard, hit **ctrl** + **cmd** + **space**)

  Run your app, and hit that button, and (fingers crossed) see your emoji appear.

### 3 ... 2 ... 1 ... 🚀

15. Finally, let's make the counter increment (good bye emojis, for now).

  For this, our ViewController is going to need a local variable. Add this line to the top of your `ViewController`:

  `var counter = 0`

  This will keep count of the taps on our button.

16. Now, let's hook up our button and our counter.

  Inside the `buttonTapped` method, increment the counter:

  `counter += 1`

17. The final step is to make the label show the latest value of the counter.

  First, delete the placeholder text "Label" from your label in the storyboard, and replace it with `0`.

  Then in the `buttonTapped` method replace the emoji inside the `"..."` with:

  `"\(counter)"`

  And ... run your app!

  ![step10](./assets/step10.gif)
