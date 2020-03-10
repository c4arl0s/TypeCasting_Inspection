# TypeCasting-Inspection
i
TypeCasting-Inspection

- When you dive into building apps you will discover that, when working with UIKit,  the APIs can return very generic obkjects, such as UIViewController. But as the developer of your application, you know what the specific type should be. 

- For example, if pressing a button on the view of FirstViewController always presents a SecondViewController, you can force the downcast of destination to SecondViewController within the prepare(for segue:) function. This function is called whenever you present a new view controller.

``` swift
import UIKit

class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
    }

    override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
        if let secondViewController = segue.destination as? SecondViewController {
        secondViewController.names = ["Carlos","Norma","Trinidad"]
    } else { print("casting failed") }
    }

    @IBAction func buttonTapped(_ sender: UIButton) {
        performSegue(withIdentifier: "goToSVC", sender: sender)
    }
}
```

