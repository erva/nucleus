# Changelog

### 09.08.2017, Version: 5.0.0

* Fork https://github.com/konmik/nucleus
* Change lifecycle. See `nucleus.view.PresenterLifecycleDelegate` 
* Updated tests
* Removed `NucleusActionBarActivity`. Use `NucleusAppCompatActivity`

### 11.07.2016, Version: 4.0.0

* Now activities and fragments drop presenters during onPause instead of onDestroy.

### 28.04.2016, Version: 3.0.0

* `onPause` and `onDestroy` were separated
* View does not became dropped on Fragment's `onPause`
* Presenters become dropped on View detachment, Fragment and Activity destruction if the
 owning activity does not have `isChangingConfigurations()` flag set to true.

### 08.04.2016, Version: 2.0.6

* Service release to eliminate some version confusion on maven central.

### 05.09.2015, Version: 2.0.0

* RxPresenter became completely usable without getView().
* OperatorSemaphore replaced with standard RxJava operators.
* Internal structure is simplified even more: removed manager and helper.
* All tests became unit tests and are testable without device.

### 09.06.2015, Version: 1.3.3

* Jar library release of core library to provide sources in IntelliJ IDEA.
 Support libraries are still in aar format because of scary compilation warnings. :D

### 09.06.2015, Version: 1.3.1

* Lazy presenter creation before the actual `onTakeView` call. In some cases this allows to initialize
  presenter dependencies before initializing presenter itself.
* `RxPresenter.add(Subscription)` method to automatically unsubscribe subscriptions on presenter destruction.

### 07.05.2015, Version: 1.3.0

* An ability to instantiate presenters with custom `PresenterFactory`, this allows
  to put arguments into a presenter's constructor or to make an instance-specific
  dependency injection.
* `NucleusAppCompatActivity`
* `@RequiresPresenter` has been moved to `nucleus.factory` package.

### 03.04.2015, Version: 1.1.2

* Separate `PresenterHelper` class for easier View class creation.

### 03.04.2015, Version: 1.1.0

* Base view classes for support libraries has been extracted to separate artifacts.
* There is a possibility to NOT put `@RequiresPresenter` annotation now.
* `@RequiresPresenter` annotation has been moved to `view` package.
* `PresenterManager` does not analyse View to find Presenter's class now. It requires presenter's class as an argument.
