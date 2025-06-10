Below are 20 common XCUITest challenges you’ll often encounter in real-world iOS UI tests

1. **Verify App Launch**

   ```swift
   func testAppLaunch() {
       let app = XCUIApplication()
       app.launch()
       XCTAssertTrue(app.buttons["mainButton"].exists)
   }
   ```

2. **Tap a Button and Verify Navigation**

   ```swift
   func testTapLoginButton() {
       let app = XCUIApplication()
       app.launch()
       app.buttons["loginButton"].tap()
       XCTAssertTrue(app.staticTexts["welcomeLabel"].waitForExistence(timeout: 5))
   }
   ```

3. **Enter Text in a Text Field**

   ```swift
   func testEnterUsername() {
       let app = XCUIApplication()
       app.launch()
       let usernameField = app.textFields["usernameField"]
       XCTAssertTrue(usernameField.exists)
       usernameField.tap()
       usernameField.typeText("test_user")
       XCTAssertEqual(usernameField.value as? String, "test_user")
   }
   ```

4. **Handle Secure Text Field**

   ```swift
   func testEnterPassword() {
       let app = XCUIApplication()
       app.launch()
       let passwordField = app.secureTextFields["passwordField"]
       passwordField.tap()
       passwordField.typeText("P@ssw0rd")
       // Secure fields return •••••, so check that it isn’t empty
       XCTAssertFalse((passwordField.value as! String).isEmpty)
   }
   ```

5. **Dismiss Keyboard**

   ```swift
   func testDismissKeyboard() {
       let app = XCUIApplication()
       app.launch()
       let field = app.textFields["searchField"]
       field.tap()
       field.typeText("hello")
       app.keyboards.buttons["Return"].tap()
       XCTAssertFalse(app.keyboards.element.exists)
   }
   ```

6. **Scroll a Table View to a Specific Cell**

   ```swift
   func testScrollToCell() {
       let app = XCUIApplication()
       app.launch()
       let table = app.tables["mainTable"]
       let cell = table.cells.element(boundBy: 20)
       table.scrollToElement(element: cell)
       XCTAssertTrue(cell.exists)
   }
   // Helper extension:
   extension XCUIElement {
       func scrollToElement(element: XCUIElement) {
           while !element.isHittable {
               swipeUp()
           }
       }
   }
   ```

7. **Scroll a Collection View**

   ```swift
   func testScrollCollection() {
       let app = XCUIApplication()
       app.launch()
       let collection = app.collectionViews["imageGrid"]
       let targetCell = collection.cells["imageCell_50"]
       collection.swipeUp() // or loop until hittable
       XCTAssertTrue(targetCell.waitForExistence(timeout: 5))
   }
   ```

8. **Swipe to Delete a Cell**

   ```swift
   func testSwipeToDelete() {
       let app = XCUIApplication()
       app.launch()
       let cell = app.tables["todoList"].cells["task_3"]
       cell.swipeLeft()
       cell.buttons["Delete"].tap()
       XCTAssertFalse(cell.exists)
   }
   ```

9. **Select from a Picker Wheel**

   ```swift
   func testSelectPickerValue() {
       let app = XCUIApplication()
       app.launch()
       app.buttons["showPicker"].tap()
       let picker = app.pickers.pickerWheels.element
       picker.adjust(toPickerWheelValue: "March")
       XCTAssertEqual(picker.value as? String, "March")
   }
   ```

10. **Toggle a Switch**

    ```swift
    func testToggleSwitch() {
        let app = XCUIApplication()
        app.launch()
        let darkModeSwitch = app.switches["darkModeSwitch"]
        let originalState = darkModeSwitch.value as! String
        darkModeSwitch.tap()
        XCTAssertNotEqual(darkModeSwitch.value as! String, originalState)
    }
    ```

11. **Adjust a Slider**

    ```swift
    func testAdjustSlider() {
        let app = XCUIApplication()
        app.launch()
        let volumeSlider = app.sliders["volumeSlider"]
        volumeSlider.adjust(toNormalizedSliderPosition: 0.7)
        XCTAssertEqual(volumeSlider.value as! String, "70%")
    }
    ```

12. **Use a Segmented Control**

    ```swift
    func testSegmentedControl() {
        let app = XCUIApplication()
        app.launch()
        let segment = app.segmentedControls["optionsSegment"]
        segment.buttons["Second"].tap()
        XCTAssertTrue(app.staticTexts["selectedSecond"].exists)
    }
    ```

13. **Handle an Alert**

    ```swift
    func testHandleAlert() {
        let app = XCUIApplication()
        app.launch()
        app.buttons["showAlert"].tap()
        let alert = app.alerts["Warning"]
        XCTAssertTrue(alert.exists)
        alert.buttons["OK"].tap()
        XCTAssertFalse(alert.exists)
    }
    ```

14. **UI Interruption Monitor (e.g., Permissions)**

    ```swift
    func testHandlePermissionAlert() {
        let app = XCUIApplication()
        addUIInterruptionMonitor(withDescription: "Permissions") { alert in
            if alert.buttons["Allow"].exists {
                alert.buttons["Allow"].tap()
                return true
            }
            return false
        }
        app.launch()
        app.buttons["accessCamera"].tap()
        app.tap() // trigger the monitor
        XCTAssertTrue(app.otherElements["cameraView"].exists)
    }
    ```

15. **Long Press Gesture**

    ```swift
    func testLongPress() {
        let app = XCUIApplication()
        app.launch()
        let element = app.images["profilePicture"]
        element.press(forDuration: 2.0)
        XCTAssertTrue(app.buttons["editPhoto"].exists)
    }
    ```

16. **Drag and Drop**

    ```swift
    func testDragAndDrop() {
        let app = XCUIApplication()
        app.launch()
        let from = app.cells["item_1"]
        let to = app.cells["item_5"]
        from.press(forDuration: 1.0, thenDragTo: to)
        XCTAssertTrue(to.images["item_1"].exists)
    }
    ```

17. **Pinch to Zoom**

    ```swift
    func testPinchToZoom() {
        let app = XCUIApplication()
        app.launch()
        let map = app.images["mapView"]
        map.pinch(withScale: 2.0, velocity: 1.0)
        // verify zoom by checking some UI change
        XCTAssertTrue(app.buttons["zoomedInButton"].exists)
    }
    ```

18. **Launch with Arguments & Environment**

    ```swift
    func testLaunchInDemoMode() {
        let app = XCUIApplication()
        app.launchArguments = ["-DemoMode", "YES"]
        app.launchEnvironment = ["UITest": "1"]
        app.launch()
        XCTAssertTrue(app.staticTexts["demoBanner"].exists)
    }
    ```

19. **Measure App Launch Performance**

    ```swift
    func testAppLaunchPerformance() {
        measure(metrics: [XCTOSSignpostMetric.applicationLaunch]) {
            XCUIApplication().launch()
        }
    }
    ```

20. **Capture and Attach a Screenshot**

    ```swift
    func testTakeScreenshot() {
        let app = XCUIApplication()
        app.launch()
        // perform some actions…
        let screenshot = XCUIScreen.main.screenshot()
        let attachment = XCTAttachment(screenshot: screenshot)
        attachment.lifetime = .keepAlways
        add(attachment)
    }
    ```
