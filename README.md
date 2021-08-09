# Pre-work: *Tip Calculator App*

**Tip Calculator** is a tip calculator application for iOS.

Submitted by: **Heggy**

Time spent: **3** hours spent in total

## User Stories

The following **required** functionality is complete:

* [ ] User can enter a bill amount, choose a tip percentage, and see the tip and total values.
* [ ] User can select between tip percentages by tapping different values on the segmented control and the tip value is updated accordingly

The following **optional** features are implemented:

* [ ] UI animations
* [ ] Remembering the bill amount across app restarts (if <10mins)
* [ ] Using locale-specific currency and currency thousands separators.
* [ ] Making sure the keyboard is always visible and the bill amount is always the first responder. This way the user doesn't have to tap anywhere to use this app. Just launch the app and start typing.

The following **additional** features are implemented:

- [ ] List anything else that you can get done to improve the app functionality!

## Video Walkthrough

Here's a walkthrough of implemented user stories:

<img src='./calc-tip-swift.gif' title='Video Walkthrough' width='' alt='Video Tip Calculator Walkthrough' />

GIF created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Challenges faced while developing this app:

* [ ] Navigating `Storyboard` to add object onto `view`
* [ ] Learning to connect outlet and actions from `Storyboard` to `viewController.swift`
* [ ] Connecting tipControl segment ui to code.

```swift
@IBAction func calculateTip(_ sender: Any) {
    // Get bill amount from text field input
    let bill = Double(billAmountTextField.text!) ?? 0
    
    // Get Total tip by multiplying tip * tipPercentage
    let tipPercentage = [0.15, 0.18, 0.2]
    let tip = bill * tipPercentage[tipControl.selectedSegmentIndex]
    let total = bill + tip
    
    // Update Tip Amount Label
    tipAmountLabel.text = String(format: "$%.2f", tip)
    // Update Total Amount
    totalLabel.text = String(format: "$%.2f", total)
}
```

## License

    Copyright 2021 Heggy

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.