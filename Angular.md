1. **How to pass data from one component to another component in Angular?**
   - Use `@Input()` to pass data from parent to child.
   - Use `@Output()` and `EventEmitter` to pass data from child to parent.
   - Utilize property binding to bind data to child component properties.
   - Example: `<app-child [data]="parentData" (dataEvent)="receiveData($event)"></app-child>`.
   - Ensure child component has corresponding `@Input` and `@Output` properties.

2. **How do you pass data between multiple components in Angular?**
   - Create a shared service to hold and manage the data.
   - Use `BehaviorSubject` or `Subject` in the service to emit data changes.
   - Inject the service into the components that need to share data.
   - Subscribe to the service’s observable in the components to receive data.
   - Update the shared service’s data from any component.

3. **How do you handle data sharing between sibling components in Angular?**
   - Use a shared service with `Subject` or `BehaviorSubject` to manage data.
   - Inject the shared service into both sibling components.
   - Sibling 1 updates the data through the service.
   - Sibling 2 subscribes to the data changes via the service.
   - This approach ensures siblings can communicate without direct interaction.

4. **What are signals in Angular? How to convert signals to observable in Angular?**
   - Signals manage state and notify when changes occur.
   - Convert signals to observables using RxJS `from` function.
   - Signals provide a declarative way to handle state changes.
   - Example: `const observable = from(signal)`.
   - Use observables for reactive programming and asynchronous operations.

5. **Do you know about server-side rendering (SSR) in Angular? Implemented?**
   - SSR improves SEO and initial load time by rendering on the server.
   - Implement SSR with Angular Universal using `ng add @nguniversal/express-engine`.
   - SSR pre-renders the HTML on the server before sending it to the client.
   - This approach enhances performance and crawlability by search engines.
   - The server sends a fully rendered page to the browser, which then bootstraps the Angular app.

6. **What is defer view in Angular?**
   - Defer view is an optimization technique.
   - It delays rendering of certain parts of the DOM until necessary.
   - Enhances performance by reducing initial load time.
   - Useful for large components or parts of the app not immediately visible.
   - Can be managed with techniques like lazy loading.

7. **What is control flow template in Angular?**
   - Structural directives like `*ngIf`, `*ngFor`, `*ngSwitch` manage control flow.
   - They conditionally add or remove elements in the DOM.
   - Provide a way to handle rendering logic directly in the template.
   - Example: `<div *ngIf="condition">Content</div>`.
   - Simplify dynamic content management in Angular templates.

8. **What is app config in Angular?**
   - Configuration settings for an Angular app.
   - Defined in `environment.ts` files for different environments (e.g., dev, prod).
   - Helps manage environment-specific settings and variables.
   - Example: `export const environment = { production: false, apiUrl: 'http://dev.api.com' };`.
   - Allows easy switching between configurations without changing the code.

9. **What is Angular Material UI?**
   - A UI component library for Angular.
   - Follows Google's Material Design principles.
   - Provides pre-built, customizable UI components like buttons, forms, and dialogs.
   - Simplifies the process of building responsive, attractive UIs.
   - Installation: `ng add @angular/material`.

10. **How to use services and interceptors in a Standalone template in Angular?**
    - Register services in the `providers` array of a standalone component.
    - Use `HTTP_INTERCEPTORS` to add interceptors.
    - Example: `@Component({ providers: [{ provide: HTTP_INTERCEPTORS, useClass: MyInterceptor, multi: true }] })`.
    - Services manage business logic and data access.
    - Interceptors handle HTTP request and response transformation globally.

11. **What is RxJS?**
    - Reactive Extensions for JavaScript.
    - A library for reactive programming using observables.
    - Facilitates asynchronous operations and event handling.
    - Provides operators for transforming, filtering, and combining streams.
    - Widely used in Angular for handling HTTP requests and event streams.

12. **What is an observable in RxJS?**
    - A stream of data that can be observed over time.
    - Can emit multiple values asynchronously.
    - Observables are lazy and only emit values when subscribed to.
    - They can handle a variety of data sources like events, HTTP requests, and more.
    - Example: `const observable = new Observable(observer => { observer.next('data'); observer.complete(); });`.

13. **Explain hot and cold observables in RxJS.**
    - Hot observables emit values regardless of subscribers.
    - Cold observables start emitting values only when there are subscribers.
    - Hot observables share the same execution context among all subscribers.
    - Cold observables create a new execution context for each subscriber.
    - Example: HTTP request observable is cold, while a WebSocket stream is hot.

14. **Commonly used RxJS operators?**
    - `map`: Transforms each value from the source observable.
    - `filter`: Emits values that pass a predicate function.
    - `switchMap`: Projects each value to an observable and cancels previous ones.
    - `mergeMap`: Projects each value to an observable and flattens them into a single stream.
    - `catchError`: Handles errors from the source observable and provides a fallback value or observable.

15. **Explain the use of switchMap and forkJoin operators in RxJS.**
    - `switchMap`: Switches to a new observable, canceling the previous one.
    - Useful for handling dependent async operations like HTTP requests.
    - `forkJoin`: Waits for multiple observables to complete and emits their last values.
    - Ideal for combining results from multiple sources once they all complete.
    - Example: `forkJoin([obs1$, obs2$]).subscribe(([res1, res2]) => { /* handle results */ });`.

16. **What is the difference between Subject and BehaviorSubject in RxJS?**
    - `Subject`: Emits new values to subscribers without retaining them.
    - `BehaviorSubject`: Emits the latest value to new subscribers immediately.
    - `Subject` is useful for simple event handling.
    - `BehaviorSubject` is suitable for managing state.
    - `BehaviorSubject` requires an initial value upon creation.

17. **Explain the difference between observables, subjects, and behavior subjects in Angular.**
    - Observables: Stream data values, lazy, multicast to multiple subscribers.
    - Subjects: Act as both observable and observer, emit values to multiple subscribers.
    - BehaviorSubjects: Retain the latest value, emit it to new subscribers immediately.
    - Use observables for data streams like HTTP requests.
    - Use subjects and behavior subjects for component communication and state management.

18. **Purpose and usage of BehaviorSubject and ReplaySubject in Angular?**
    - `BehaviorSubject`: Maintain and provide the latest state to new subscribers.
    - Emit the current value immediately upon subscription.
    - `ReplaySubject`: Cache and emit a specified number of past values to new subscribers.
    - Useful for scenarios where subscribers need historical data.
    - Example: `const replaySubject = new ReplaySubject(3); replaySubject.next('value1');`.

19. **What is Angular? What are the advantages of Angular?**
    - Angular is a platform and framework for building single-page client applications using HTML and TypeScript.
    - Advantages:
      - Two-way data binding simplifies data handling.
      - Dependency injection improves code modularity and testability.
      - Built-in directives and components enhance productivity.
      - TypeScript offers static typing, reducing runtime errors.
      - Angular CLI streamlines development and project management.

20. **What is Angular CLI? How does Angular CLI handle component dependencies when you add a component to your project?**
    - Angular CLI is a command-line interface tool to initialize, develop, scaffold, and maintain Angular applications.
    - Automatically updates `app.module.ts` to include the new component.
    - Adds the new component to the declarations array.
    - Provides commands to generate components, services, and other artifacts.
    - Simplifies project setup and configuration with sensible defaults.

21. **How do you create a standalone component using Angular CLI?**
    - Use the command: `ng generate component component-name --standalone`.
    - This creates a component that is not declared in any NgModule.
    - It can be used directly in other components or applications.
    - Standalone components have their own imports and providers.
    - Example: `ng g c my-standalone --standalone`.

22. **What are life cycle hooks in Angular?**
    - Angular provides hooks to tap into different phases of a component's lifecycle.
    - Common hooks:
      - `ngOnInit()`: Called after component initialization.
      - `ngOnChanges()`: Called when input properties change.
      - `ngDoCheck()`: Called during every change detection run.
      - `ngOnDestroy()`: Called just before the component is destroyed.
    - These hooks allow you to run custom logic at specific points in a component's lifecycle.

23. **What is the latest version of Angular? What are the new features in Angular 17?**
    - Angular 17 is the latest version as of this writing.
    - New features include:
      - Improved performance and smaller bundle sizes.
      - Enhanced support for standalone components and APIs.
      - Simplified configuration and setup for Angular Universal.
      - New directives for better template control and conditional rendering.
      - Updated Angular Material components and theming options.

24. **What are pipes in Angular? Describe the difference between pure and impure pipes in Angular.**
    - Pipes transform data in templates.
    - Pure pipes: Only re-evaluate when input changes; default type.
    - Impure pipes: Re-evaluate on every change detection run.
    - Pure pipes are more performant but less flexible.
    - Example of pure pipe: `{{ value | uppercase }}`
    - Example of impure pipe: `@Pipe({name: 'impurePipe', pure: false})`

25. **When would you use each type of pipe, and what are the implications for performance?**
    - Use pure pipes for data that doesn’t change often to optimize performance.
    - Use impure pipes for dynamic data that changes frequently.
    - Pure pipes ensure fewer re-calculations, enhancing performance.
    - Impure pipes can cause performance issues if overused due to frequent re-evaluations.
    - Evaluate the trade-off between data freshness and performance needs.

26. **Have you heard about async pipes? Can you explain if they are pure or impure?**
    - Async pipes automatically subscribe to and handle observable streams.
    - They are considered impure because they update the view whenever a new value is emitted.
    - Simplify handling of observables in templates.
    - Example: `{{ observable$ | async }}`
    - They manage subscription and unsubscription, preventing memory leaks.

27. **How do you use custom pipes in Angular components?**
    - Create a custom pipe with the `@Pipe` decorator.
    - Implement the `transform` method for data transformation.
    - Declare the pipe in an NgModule or as a standalone.
    - Use the custom pipe in templates: `{{ value | customPipe }}`.
    - Example: 
      ```typescript
      @Pipe({name: 'customPipe'})
      export class CustomPipe implements PipeTransform {
        transform(value: string): string {
          return value.toUpperCase();
        }
      }
      ```

28. **What are the types of subjects in Angular?**
    - `Subject`: Basic subject without initial value.
    - `BehaviorSubject`: Holds the latest value and emits it to new subscribers.
    - `ReplaySubject`: Replays a specified number of past values to new subscribers.
    - `AsyncSubject`: Emits the last value to subscribers when the observable completes.
    - These subjects are part of RxJS and used for various scenarios in Angular applications.

29. **What is the benefit of using subject in Angular?**
    - Facilitates communication between components.
    - Acts as both an observable and an observer.
    - Allows multicasting to multiple subscribers.
    - Useful for implementing event buses and shared services.
    - Enhances reactivity and state management in Angular applications.

30. **Can you explain the difference between AOT (Ahead-of-Time) and JIT (Just-in-Time) compilation in Angular?**
    - AOT compiles the application during the build process.
    - JIT compiles the application in the browser at runtime.
    - AOT improves load time and security by reducing the need for the Angular compiler in the client.
    - JIT is useful during development for faster builds and ease of debugging.
    - AOT is generally preferred for production deployments due to its performance benefits.

31. **ngrx? How to use ngrx in a Standalone template in Angular?**
    - NgRx is a state management library for Angular based on Redux.
    - Install NgRx with `npm install @ngrx/store @ngrx/effects`.
    - Define actions, reducers, and selectors for state management.
    - Register the store in your standalone component’s `providers` array.
    - Use NgRx effects for handling side effects like HTTP requests.
    - Example: 
      ```typescript
      @Component({
        standalone: true,
        providers: [provideStore({ reducer }), provideEffects([MyEffects])]
      })
      export class MyComponent { }
      ```

32. **What is an Angular interceptor, and how is it used?**
    - Interceptors intercept HTTP requests and responses.
    - Implement the `HttpInterceptor` interface.
    - Use the `intercept` method to modify requests or responses.
    - Register interceptors in the `providers` array with `HTTP_INTERCEPTORS`.
    - Example: 
      ```typescript
      @Injectable()
      export class AuthInterceptor implements HttpInterceptor {
        intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {
          const clonedReq = req.clone({ headers: req.headers.set('Authorization', 'Bearer token') });
          return next.handle(clonedReq);
        }
      }
      ```

33. **Explain the concept of interceptor hierarchy in Angular.**
    - Interceptors are executed in the order they are provided.
    - Multiple interceptors can be layered to handle different concerns.
    - The order of execution can be controlled by the order of providers.
    - Subsequent interceptors can modify the request/response further.
    - Allows separation of concerns, such as authentication, logging, and error handling.

34. **How do interceptors intercept HTTP requests and responses?**
    - Interceptors modify the `HttpRequest` object before passing it to the next handler.
    - They can also modify the `HttpResponse` object before it reaches the application.
    - Use `HttpHandler` to forward the modified request or response.
    - Provide a mechanism to globally handle authentication, logging, etc.
    - Interceptors must return an observable that completes.

35. **How does routing work with standalone components?**
    - Define routes in the standalone component using `RouterModule`.
    - Example: 
      ```typescript
      @Component({
        standalone: true,
        imports: [RouterModule.forRoot(routes)],
        template: '<router-outlet></router-outlet>'
      })
      export class AppComponent { }
      ```
    - Configure the routes array with component mappings.
    - Use `routerLink` directives to navigate between routes.
    - Standalone components can be used as route targets directly.

36. **What is Standalone template in Angular? Explain how bootstrapping works with standalone components.**
    - Standalone templates allow components to be used without declaring them in NgModules.
    - Bootstrapping standalone components involves using `bootstrapApplication` instead of `bootstrapModule`.
    - Simplifies component usage and reduces the need for NgModules.
    - Example: 
      ```typescript
      bootstrapApplication(AppComponent);
      ```
    - Standalone components include their own dependencies and configurations.

37. **What are standalone components in Angular?**
    - Components that are not declared in any NgModule.
    - Can be used independently or in combination with other standalone components.
    - Include their own dependencies and providers.
    - Simplify modularization and reuse of components.
    - Introduced to reduce the overhead of NgModules and streamline Angular applications.

38. **What is formBuilder in Angular, and how is it used?**
    - FormBuilder is a service for creating form controls in Angular.
    - Simplifies the creation of `FormGroup`, `FormControl`, and `FormArray`.
    - Provides methods like `group`, `control`, and `array` to initialize forms.
    - Example: 
      ```typescript
      this.form = this.fb.group({
        name: ['', Validators.required],
        age: [null, Validators.min(0)]
      });
      ```
    - Reduces boilerplate code when setting up reactive forms.

39. **What is the purpose of FormBuilder and FormGroup?**
    - `FormBuilder` helps in creating and managing form controls.
    - `FormGroup` is a collection of form controls that can be validated as a group.
    - Use `FormBuilder` to instantiate `FormGroup` with a configuration object.
    - Simplifies reactive form setup and management.
    - Example: 
      ```typescript
      const form = this.fb.group({
        firstName: ['', Validators.required],
        lastName: ['', Validators.required]
      });
      ```

40. **How do you improve the performance of an Angular application?**
    - Use lazy loading to load modules only when needed.
    - Implement OnPush change detection strategy to reduce change detection cycles.
    - Optimize bundle size using tree shaking and AOT compilation.
    - Avoid unnecessary data binding and DOM manipulation.
    - Use Angular CLI build optimizations like production mode (`ng build --prod`).

41. **What steps do you take to optimize the performance of your Angular project if it's taking too much time to load?**
    - Implement code splitting and lazy loading.
    - Minimize and compress assets (images, CSS, JavaScript).
    - Optimize change detection by using `OnPush` strategy.
    - Remove unused dependencies and code.
    - Enable AOT compilation and tree shaking for smaller bundle sizes.

42. **What are directives in Angular, and what are the different types?**
    - Directives are classes that add behavior to elements in Angular templates.
    - Three types:
      - Component directives (with a template).
      - Structural directives (like `ngIf`, `ngFor`) that change the DOM structure.
      - Attribute directives (like `ngClass`, `ngStyle`) that change the appearance or behavior of elements.
    - Directives extend HTML with custom attributes and elements.
    - Example of custom directive: 
      ```typescript
      @Directive({
        selector: '[appHighlight]'
      })
      export class HighlightDirective {
        @HostBinding('style.backgroundColor') bgColor = 'yellow';
      }
      ```

43. **Explain structural and behavioral directives.**
    - Structural directives change the DOM layout by adding or removing elements.
    - Examples: `*ngIf`, `*ngFor`, `*ngSwitch`.
    - Behavioral (attribute) directives change the appearance or behavior of elements.
    - Examples: `ngClass`, `ngStyle`.
    - Structural directives modify the structure, while attribute directives modify attributes.

44. **What are the ngIf, ngFor, and ngSwitch directives used for?**
    - `ngIf`: Conditionally includes an element in the DOM.
      - Example: `<div *ngIf="condition">Content</div>`.
    - `ngFor`: Repeats a template for each item in a list.
      - Example: `<div *ngFor="let item of items">{{ item }}</div>`.
    - `ngSwitch`: Conditionally switches between multiple templates.
      - Example: 
        ```html
        <div [ngSwitch]="value">
          <div *ngSwitchCase="1">Case 1</div>
          <div *ngSwitchCase="2">Case 2</div>
          <div *ngSwitchDefault>Default</div>
        </div>
        ```

45. **Custom directives in Angular?**
    - Custom directives allow you to create reusable behavior and appearance modifications.
    - Created with the `@Directive` decorator.
    - Example: 
      ```typescript
      @Directive({
        selector: '[appHighlight]'
      })
      export class HighlightDirective {
        @HostBinding('style.backgroundColor') bgColor: string;

        @HostListener('mouseenter') onMouseEnter() {
          this.bgColor = 'yellow';
        }

        @HostListener('mouseleave') onMouseLeave() {
          this.bgColor = 'transparent';
        }
      }
      ```
    - Use custom directives to encapsulate and reuse common behaviors.


46. **How can you use zone.js for asynchronous programming in Angular? How does it affect change detection?**
    - Zone.js patches asynchronous APIs to capture async operations and keep track of their context.
    - Angular uses Zone.js to automatically trigger change detection after async tasks complete.
    - It allows automatic synchronization between the model and the view.
    - Simplifies handling of asynchronous tasks without manually managing change detection.
    - Improves the developer experience by reducing boilerplate code for updates.

47. **What is the purpose of using guards in Angular routing? Can you explain their types and usage?**
    - Guards control navigation to and from routes.
    - Types:
      - `CanActivate`: Prevents navigation to a route.
      - `CanDeactivate`: Prevents leaving a route.
      - `Resolve`: Fetches data before route activation.
      - `CanLoad`: Prevents loading of lazy-loaded routes.
    - Example: 
      ```typescript
      @Injectable()
      export class AuthGuard implements CanActivate {
        canActivate(): boolean {
          return this.authService.isLoggedIn();
        }
      }
      ```
    - Guards ensure secure and efficient routing in applications.

48. **What are Angular services?**
    - Services provide shared functionality across components.
    - Used for data sharing, business logic, and API communication.
    - Created with the `@Injectable` decorator.
    - Example: 
      ```typescript
      @Injectable()
      export class DataService {
        getData() {
          return this.http.get('/api/data');
        }
      }
      ```
    - Services enhance modularity and reusability in Angular applications.

49. **How to pass headers in Angular services?**
    - Use `HttpHeaders` to set headers for HTTP requests.
    - Example: 
      ```typescript
      const headers = new HttpHeaders().set('Authorization', 'Bearer token');
      this.http.get('/api/data', { headers });
      ```
    - Headers can be set for individual requests or globally using interceptors.
    - Allows for secure and authenticated communication with APIs.

50. **Can you discuss your experience with Angular services and dependency injection?**
    - Angular services are pivotal for modular and maintainable code.
    - Dependency injection (DI) allows services to be injected into components and other services.
    - DI improves testability by allowing mock implementations.
    - Services handle business logic, API calls, and shared state management.
    - Example: Injecting a service into a component:
      ```typescript
      constructor(private dataService: DataService) { }
      ```

51. **What is the `@Injectable` decorator in Angular services?**
    - Marks a class as available to be provided and injected as a dependency.
    - Enables Angular’s DI system to resolve dependencies.
    - Can specify the providedIn option to control the service’s scope.
    - Example: 
      ```typescript
      @Injectable({
        providedIn: 'root'
      })
      export class AuthService { }
      ```
    - Ensures that services are provided in the appropriate context.

52. **How do you handle errors in Angular services?**
    - Use RxJS `catchError` operator to handle errors in HTTP requests.
    - Example: 
      ```typescript
      this.http.get('/api/data').pipe(
        catchError(error => {
          console.error('Error occurred:', error);
          return throwError(error);
        })
      );
      ```
    - Implement global error handling with interceptors.
    - Provide user-friendly error messages and log errors for debugging.
    - Use retry mechanisms for transient errors.

53. **Can we inject a service without using the constructor in a component?**
    - Yes, by using the `inject` function introduced in Angular 14.
    - Example: 
      ```typescript
      import { inject } from '@angular/core';

      @Component({ ... })
      export class MyComponent {
        private myService = inject(MyService);
      }
      ```
    - This provides a more flexible and concise way to inject services.
    - Useful in scenarios where constructor injection is not possible or practical.

54. **What are some common class decorators in Angular?**
    - `@Component`: Defines a component.
    - `@Directive`: Defines a directive.
    - `@Pipe`: Defines a pipe.
    - `@Injectable`: Marks a class as injectable for DI.
    - `@NgModule`: Defines an Angular module.
    - Example: 
      ```typescript
      @Component({
        selector: 'app-my-component',
        template: '<div>My Component</div>'
      })
      export class MyComponent { }
      ```

55. **Can you provide examples of when you would use each decorator?**
    - `@Component`: Use to create a new UI component.
    - `@Directive`: Use to create reusable behavior to apply to elements.
    - `@Pipe`: Use to create custom transformations for template values.
    - `@Injectable`: Use to make a class available for DI.
    - `@NgModule`: Use to define a module that bundles components, directives, pipes, and services.

56. **Can you explain the purpose of host binding and host listener decorators?**
    - `@HostBinding`: Binds a property to the host element.
    - Example: 
      ```typescript
      @Directive({
        selector: '[appHighlight]'
      })
      export class HighlightDirective {
        @HostBinding('style.backgroundColor') bgColor = 'yellow';
      }
      ```
    - `@HostListener`: Listens to events on the host element.
    - Example: 
      ```typescript
      @Directive({
        selector: '[appHighlight]'
      })
      export class HighlightDirective {
        @HostListener('mouseenter') onMouseEnter() {
          this.bgColor = 'yellow';
        }
      }
      ```
    - Both decorators enhance interaction and control over the host element.

57. **How do you handle CORS errors in Angular?**
    - Configure the backend server to allow cross-origin requests.
    - Use `HttpHeaders` to set appropriate headers in Angular HTTP requests.
    - Example:
      ```typescript
      const headers = new HttpHeaders().set('Access-Control-Allow-Origin', '*');
      this.http.get('/api/data', { headers });
      ```
    - Use proxies during development to bypass CORS issues.
    - Ensure proper configuration on both client and server sides to resolve CORS errors.

58. **What is the purpose of Angular's view encapsulation?**
    - Encapsulates component styles to prevent them from affecting other components.
    - Types:
      - `Emulated`: Default, emulates Shadow DOM behavior using scoped styles.
      - `None`: No encapsulation, styles affect the global scope.
      - `ShadowDom`: Uses native Shadow DOM for true encapsulation.
    - Example:
      ```typescript
      @Component({
        selector: 'app-my-component',
        encapsulation: ViewEncapsulation.Emulated,
        template: '<div>My Component</div>'
      })
      export class MyComponent { }
      ```
    - Enhances component isolation and style scoping.

59. **What is a shared module in Angular?**
    - A module that exports commonly used components, directives, pipes, and services.
    - Simplifies reusability and reduces code duplication.
    - Import shared module into other feature modules as needed.
    - Example:
      ```typescript
      @NgModule({
        declarations: [CommonComponent],
        exports: [CommonComponent],
        imports: [CommonModule]
      })
      export class SharedModule { }
      ```
    - Promotes DRY (Don't Repeat Yourself) principles in Angular applications.

60. **Can you explain lazy loading in Angular and how it works?**
    - Lazy loading delays the loading of feature modules until they are needed.
    - Improves initial load time by reducing the size of the main bundle.
    - Configure lazy loading in the routing module with `loadChildren`.
    - Example:
      ```typescript
      const routes: Routes = [
        { path: 'feature', loadChildren: () => import('./feature/feature.module').then(m => m.FeatureModule) }
      ];
      ```
    - Lazy loading optimizes performance by loading code on demand.

61. **Can you explain the concept of property binding, event binding, and interpolation in Angular? What is two-way binding?**
    - Property binding: Binds a property to an element attribute.
      - Example: `<input [value]="value">`.
    - Event binding: Binds an event to a method.
      - Example: `<button (click)="handleClick()">Click</button>`.
    - Interpolation: Inserts expressions into the template.
      - Example: `{{ value }}`.
    - Two-way binding: Combines property and event binding using `ngModel`.
      - Example: `<input [(ngModel)]="value">`.
    - Enables dynamic interaction between the model and the view.

62. **What are components in Angular?**
    - Building blocks of Angular applications.
    - Consist of a template, styles, and logic.
    - Defined with the `@Component` decorator.
    - Example:
      ```typescript
      @Component({
        selector: 'app-my-component',
        template: '<div>My Component</div>',
        styles: ['div { color: red; }']
      })
      export class MyComponent { }
      ```
    - Components encapsulate UI and behavior.

63. **Have you customized any Angular Material components, or have you created your own custom components using Angular Material?**
    - Yes, customize Angular Material components by overriding CSS styles.
    - Example: 
      ```css
      .mat-button {
        background-color: blue;
      }
      ```
    - Create custom components using Angular Material's design system.
    - Use Angular Material's them

ing system to apply custom themes.
    - Customize component templates and styles as per requirements.
    - Ensures a consistent look and feel across the application.

64. **How can you use Angular CLI to generate a new component, service, or module?**
    - Generate a new component:
      - Command: `ng generate component my-component`
    - Generate a new service:
      - Command: `ng generate service my-service`
    - Generate a new module:
      - Command: `ng generate module my-module`
    - CLI automates scaffolding of Angular components, services, and modules.
    - Example:
      ```sh
      ng generate component my-component
      ```
    - Ensures adherence to Angular's best practices and conventions.

65. **What are the different types of modules in Angular?**
    - Root module: Bootstraps the Angular application.
    - Feature module: Encapsulates a specific feature of the application.
    - Shared module: Contains common components, directives, pipes, and services.
    - Core module: Contains singleton services and application-wide providers.
    - Lazy-loaded module: Loaded on demand to optimize performance.
    - Each module serves a distinct purpose and enhances modularity and maintainability.

66. **What are the best practices for structuring Angular applications?**
    - Organize code by feature modules.
    - Use shared and core modules for reusable components and services.
    - Implement lazy loading for feature modules.
    - Follow Angular Style Guide for naming conventions and code organization.
    - Use services for business logic and state management.
    - Use Angular CLI for project scaffolding and consistent code structure.

67. **What is the use of Angular Schematics?**
    - Tool for code generation and transformations.
    - Used by Angular CLI to generate and modify code files.
    - Custom schematics can automate repetitive tasks and enforce best practices.
    - Example: Create a schematic to generate a custom component structure.
    - Schematics enhance productivity and maintain code consistency.

68. **What is the role of Angular Elements?**
    - Angular Elements allows Angular components to be used as custom elements (web components).
    - Facilitates integration of Angular components in non-Angular environments.
    - Example:
      ```typescript
      import { createCustomElement } from '@angular/elements';
      const myElement = createCustomElement(MyComponent, { injector: this.injector });
      customElements.define('my-element', myElement);
      ```
    - Enables reuse of Angular components across different projects and frameworks.

69. **What is Angular Universal, and why is it used?**
    - Angular Universal provides server-side rendering (SSR) for Angular applications.
    - Improves performance and SEO by rendering pages on the server.
    - Example:
      ```typescript
      import { renderModule } from '@angular/platform-server';
      renderModule(AppServerModule, { document: '<app-root></app-root>', url: '/' })
        .then(html => console.log(html));
      ```
    - Enhances user experience with faster initial page loads and better search engine indexing.

70. **What are Angular animations, and how are they implemented?**
    - Angular animations create dynamic effects within the application.
    - Defined using the `@angular/animations` module.
    - Example:
      ```typescript
      import { trigger, state, style, transition, animate } from '@angular/animations';
      @Component({
        selector: 'app-my-component',
        template: '<div [@fadeInOut]="state">Content</div>',
        animations: [
          trigger('fadeInOut', [
            state('in', style({ opacity: 1 })),
            transition(':enter', [ style({ opacity: 0 }), animate('500ms ease-in') ]),
            transition(':leave', [ animate('500ms ease-out', style({ opacity: 0 })) ])
          ])
        ]
      })
      export class MyComponent { }
      ```
    - Enhance user experience by adding visual feedback and transitions.
71. **What is the purpose of the environment.ts file in Angular?**
    - Stores environment-specific configurations.
    - Allows different settings for development, production, and other environments.
    - Example:
      ```typescript
      export const environment = {
        production: false,
        apiUrl: 'http://localhost:3000/api'
      };
      ```
    - Access environment variables throughout the application.
    - Simplifies switching between environments by changing configuration files.

72. **How do you improve the performance of an Angular application?**
    - Implement lazy loading for feature modules.
    - Use Ahead-of-Time (AOT) compilation for faster initial loads.
    - Optimize change detection with `OnPush` strategy.
    - Minimize bundle size with tree shaking and code splitting.
    - Use efficient data structures and caching mechanisms.

73. **What is Angular Material and how is it used?**
    - A UI component library for Angular.
    - Provides pre-built UI components following Google's Material Design guidelines.
    - Example:
      ```typescript
      import { MatButtonModule } from '@angular/material/button';
      @NgModule({
        imports: [MatButtonModule],
        exports: [MatButtonModule]
      })
      export class AppModule { }
      ```
    - Simplifies and accelerates UI development with consistent and customizable components.
    - Offers responsive design and accessibility out-of-the-box.

74. **How can you reset a form in Angular after submission?**
    - Use `form.reset()` to reset the form's state.
    - Example:
      ```typescript
      onSubmit() {
        this.myForm.reset();
      }
      ```
    - Resetting the form clears all input fields and sets form controls to their initial states.
    - Optionally, pass an object to `reset()` to set specific default values:
      ```typescript
      this.myForm.reset({ name: '', age: null });
      ```

75. **What is tree shaking in Angular?**
    - A technique to remove unused code from the final bundle.
    - Reduces the application size by eliminating dead code.
    - Enabled by default with the Angular CLI using Webpack.
    - Example: Unused imports and functions are not included in the production build.
    - Improves application performance by decreasing load times.

76. **How do you unsubscribe from subscriptions in Angular?**
    - Use the `unsubscribe` method to prevent memory leaks.
    - Example:
      ```typescript
      private subscription: Subscription;
      ngOnInit() {
        this.subscription = this.myService.getData().subscribe();
      }
      ngOnDestroy() {
        this.subscription.unsubscribe();
      }
      ```
    - Use `takeUntil` operator for automatic unsubscription.
    - Example:
      ```typescript
      private destroy$ = new Subject<void>();
      ngOnInit() {
        this.myService.getData().pipe(takeUntil(this.destroy$)).subscribe();
      }
      ngOnDestroy() {
        this.destroy$.next();
        this.destroy$.complete();
      }
      ```

77. **What is Angular CLI, and how does it handle component dependencies?**
    - A command-line interface for Angular development.
    - Automates project setup, build processes, and code generation.
    - Handles component dependencies by importing required modules.
    - Example: `ng generate component my-component` automatically adds the component to the app module.
    - Provides commands for serving, testing, and deploying Angular applications.

78. **How do you conditionally apply classes in Angular templates?**
    - Use `ngClass` directive for conditional class application.
    - Example:
      ```typescript
      <div [ngClass]="{ 'active': isActive, 'disabled': isDisabled }">Content</div>
      ```
    - Apply multiple classes based on different conditions.
    - Enhances dynamic styling based on component state.

79. **What is Angular Universal, and how is it used?**
    - Angular Universal provides server-side rendering (SSR) for Angular applications.
    - Improves performance and SEO by rendering pages on the server.
    - Example:
      ```typescript
      import { renderModule } from '@angular/platform-server';
      renderModule(AppServerModule, { document: '<app-root></app-root>', url: '/' })
        .then(html => console.log(html));
      ```
    - Enhances user experience with faster initial page loads and better search engine indexing.

80. **What is the purpose of Angular's view encapsulation?**
    - Encapsulates component styles to prevent them from affecting other components.
    - Types:
      - `Emulated`: Default, emulates Shadow DOM behavior using scoped styles.
      - `None`: No encapsulation, styles affect the global scope.
      - `ShadowDom`: Uses native Shadow DOM for true encapsulation.
    - Example:
      ```typescript
      @Component({
        selector: 'app-my-component',
        encapsulation: ViewEncapsulation.Emulated,
        template: '<div>My Component</div>'
      })
      export class MyComponent { }
      ```
    - Enhances component isolation and style scoping.

81. **How can you add dynamic validation to controls in Angular?**
    - Use `setValidators` method to dynamically set validators.
    - Example:
      ```typescript
      this.form.get('name').setValidators([Validators.required, Validators.minLength(3)]);
      this.form.get('name').updateValueAndValidity();
      ```
    - Modify validation rules based on runtime conditions.
    - Enhance form validation flexibility.

82. **What are validators used for in reactive forms?**
    - Validators enforce rules on form control values.
    - Built-in validators include `required`, `minLength`, `maxLength`, `pattern`, etc.
    - Example:
      ```typescript
      this.form = this.fb.group({
        name: ['', [Validators.required, Validators.minLength(3)]]
      });
      ```
    - Custom validators can be created to enforce complex rules.
    - Ensure form data integrity and validity.

83. **What is Angular Elements, and why is it used?**
    - Angular Elements allows Angular components to be used as custom elements (web components).
    - Facilitates integration of Angular components in non-Angular environments.
    - Example:
      ```typescript
      import { createCustomElement } from '@angular/elements';
      const myElement = createCustomElement(MyComponent, { injector: this.injector });
      customElements.define('my-element', myElement);
      ```
    - Enables reuse of Angular components across different projects and frameworks.

84. **What are the types of validators available for reactive forms in Angular?**
    - Built-in validators: `required`, `minLength`, `maxLength`, `pattern`, `email`, etc.
    - Example:
      ```typescript
      this.form = this.fb.group({
        email: ['', [Validators.required, Validators.email]]
      });
      ```
    - Custom validators: Define complex rules as functions.
    - Async validators: Validate data with asynchronous operations.
    - Ensure robust form validation to maintain data integrity.

85. **How do you handle large datasets in Angular, either through pagination, infinite scrolling, or local storage?**
    - Pagination: Split data into pages to reduce load.
      - Example: Use ngx-pagination library for easy implementation.
    - Infinite scrolling: Load more data as the user scrolls.
      - Example: Use ngx-infinite-scroll library.
    - Local storage: Cache data locally to minimize API calls.
      - Example: Use `localStorage` or `IndexedDB` for storing data.
    - Use efficient data structures and lazy loading to optimize performance.
    - Combine these techniques to handle large datasets effectively.

86. **What are lifecycle hooks in Angular?**
    - Methods that provide visibility into key moments in the component's lifecycle.
    - Common hooks include:
      - `ngOnInit`: Called once the component is initialized.
      - `ngOnChanges`: Called when input properties change.
      - `ngDoCheck`: Custom change detection.
      - `ngAfterViewInit`: Called after the component's view has been initialized.
      - `ngOnDestroy`: Cleanup before the component is destroyed.
    - Example:
      ```typescript
      ngOnInit() {
        // Initialization logic here
      }
      ngOnDestroy() {
        // Cleanup logic here
      }
      ```
    - Helps manage component state and resources effectively.

87. **How do you handle CORS errors in Angular?**
    - Configure the server to include appropriate CORS headers.
    - Example:
      ```http
      Access-Control-Allow-Origin: *
      Access-Control-Allow-Methods: GET, POST, PUT, DELETE
      Access-Control-Allow-Headers: Content-Type
      ```
    - Use a proxy configuration in Angular during development.
    - Example:
      ```json
      // proxy.conf.json
      {
        "/api": {
          "target": "http://localhost:3000",
          "secure": false
        }
      }
      ```
    - Update `angular.json` to use the proxy:
      ```json
      "serve": {
        "options": {
          "proxyConfig": "src/proxy.conf.json"
        }
      }
      ```

88. **How do you handle errors for observables in Angular?**
    - Use the `catchError` operator to handle errors.
    - Example:
      ```typescript
      import { catchError } from 'rxjs/operators';
      this.myService.getData().pipe(
        catchError(error => {
          // Handle error
          return of([]);
        })
      ).subscribe();
      ```
    - Use `HttpInterceptor` to handle HTTP errors globally.
    - Example:
      ```typescript
      intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {
        return next.handle(req).pipe(
          catchError(error => {
            // Handle error
            return throwError(error);
          })
        );
      }
      ```
    - Provide user-friendly error messages and log errors for debugging.

89. **What is the difference between NGOnInit and the Constructor in Angular?**
    - `constructor`: Used for dependency injection and initialization.
    - `ngOnInit`: Called after Angular initializes the component's input properties.
    - Example:
      ```typescript
      constructor(private service: MyService) {
        // Dependency injection
      }
      ngOnInit() {
        // Initialization logic here
      }
      ```
    - Use `ngOnInit` for initialization logic to ensure input properties are set.
    - Separates dependency injection and initialization concerns.

90. **What is the purpose of the app initializer in Angular?**
    - Runs custom initialization logic during application startup.
    - Example:
      ```typescript
      import { APP_INITIALIZER } from '@angular/core';
      export function initializeApp(myService: MyService) {
        return (): Promise<any> => {
          return myService.loadData();
        }
      }
      @NgModule({
        providers: [
          { provide: APP_INITIALIZER, useFactory: initializeApp, deps: [MyService], multi: true }
        ]
      })
      export class AppModule { }
      ```
    - Ensures required data or settings are loaded before the application starts.
    - Enhances control over application startup processes.

91. **What is the purpose of the angular.json file?**
    - Configuration file for Angular CLI projects.
    - Contains settings for build, serve, test, and other CLI commands.
    - Example:
      ```json
      {
        "projects": {
          "my-app": {
            "architect": {
              "build": {
                "options": {
                  "outputPath": "dist/my-app",
                  "index": "src/index.html",
                  "main": "src/main.ts",
                  "polyfills": "src/polyfills.ts",
                  "tsConfig": "tsconfig.app.json"
                }
              }
            }
          }
        }
      }
      ```
    - Centralizes project configuration and simplifies management.
    - Enables customization of CLI behavior and project settings.

92. **How do you configure environment-specific settings in an Angular project?**
    - Define environment files for different environments (e.g., `environment.ts`, `environment.prod.ts`).
    - Example:
      ```typescript
      // environment.ts
      export const environment = {
        production: false,
        apiUrl: 'http://localhost:3000/api'
      };
      // environment.prod.ts
      export const environment = {
        production: true,
        apiUrl: 'https://api.example.com'
      };
      ```
    - Use file replacements in `angular.json` to switch environments.
    - Example:
      ```json
      "fileReplacements": [
        {
          "replace": "src/environments/environment.ts",
          "with": "src/environments/environment.prod.ts"
        }
      ]
      ```
    - Access environment variables in the application code:
      ```typescript
      import { environment } from '../environments/environment';
      console.log(environment.apiUrl);
      ```

93. **What is the difference between dependencies and devDependencies in package.json?**
    - `dependencies`: Libraries required for the application to run.
    - Example:
      ```json
      "dependencies": {
        "@angular/core": "^12.0.0",
        "rxjs": "^6.6.0"
      }
      ```
    - `devDependencies`: Tools required for development, testing, and building the application.
    - Example:
      ```json
      "devDependencies": {
        "@angular/cli": "^12.0.0",
        "typescript": "^4.2.4"
      }
      ```
    - `dependencies` are included in the production build, while `devDependencies` are not.
    - Keeps the production bundle lean by excluding development-only packages.

94. **What is the difference between for...of and for...in loops in JavaScript?**
    - `for...of`: Iterates over iterable objects (arrays, strings, maps, etc.).
    - Example:
      ```javascript
      const arr = [10, 20, 30];
      for (const value of arr) {
        console.log(value); // 10, 20, 30
      }
      ```
    - `for...in`: Iterates over enumerable properties of an object.
    - Example:
      ```javascript
      const obj = { a: 1, b: 2, c: 3 };
      for (const key in obj) {
        console.log(key); // a, b, c
      }
      ```
    - `for...of` is suitable for iterating over values, while `for...in` is for keys.
    - Avoid `for...in` for arrays due to potential prototype pollution.

95. **What is data binding in Angular?**
    - Mechanism for coordinating the component's data with the view.
    - Types:
      - Interpolation: `{{ expression }}`
      - Property binding: `[property]="expression"`
      - Event binding: `(event)="handler"`
      - Two-way binding: `[(ngModel)]="property"`
    - Example:
      ```typescript
      <input [value]="name" (input)="name = $event.target.value">
      <p>Hello, {{ name }}!</p>
      ```
    - Facilitates dynamic interaction between the model and the view.
    - Enhances the responsiveness and interactivity of the application.

96. **How do you handle memory leaks in Angular?**
    - Unsubscribe from observables to prevent memory leaks.
    - Example:
      ```typescript
      ngOnDestroy() {
        this.subscription.unsubscribe();
      }
      ```
    - Use `takeUntil` to manage observable subscriptions.
    - Example:
      ```typescript
      private destroy$ = new Subject<void>();
      ngOnInit() {
        this.myService.getData().pipe(takeUntil(this.destroy$)).subscribe();
      }
      ngOnDestroy() {
        this.destroy$.next();
        this.destroy$.complete();
      }
      ```
    - Clean up event listeners and DOM elements in `ngOnDestroy`.
    - Use Angular's `ngOnDestroy` lifecycle hook for cleanup logic.

97. **What are components in Angular?**
    - Building blocks of an Angular application.
    - Each component consists of a TypeScript class, an HTML template, and optional styles.
    - Example:
      ```typescript
      @Component({
        selector: 'app-example',
        template: '<h1>Hello, {{name}}!</h1>',
        styleUrls: ['./example.component.css']
      })
      export class ExampleComponent {
        name: string = 'World';
      }
      ```
    - Components encapsulate the view and behavior for a part of the UI.
    - Facilitates modular, reusable, and maintainable code.

98. **What are Angular services?**
    - Singleton objects used to share data and functionality across components.
    - Example:
      ```typescript
      @Injectable({ providedIn: 'root' })
      export class DataService {
        private data: string;
        setData(data: string) { this.data = data; }
        getData() { return this.data; }
      }
      ```
    - Use `@Injectable` decorator to define a service.
    - Services are injected into components or other services via dependency injection.
    - Facilitates separation of concerns by moving business logic out of components.

99. **What is the difference between Subject and BehaviorSubject in RxJS?**
    - `Subject`: Does not hold a current value, emits values to new subscribers from the point of subscription.
    - Example:
      ```typescript
      const subject = new Subject<number>();
      subject.subscribe(value => console.log(value));
      subject.next(1); // Output: 1
      subject.next(2); // Output: 2
      ```
    - `BehaviorSubject`: Holds a current value, emits the latest value to new subscribers.
    - Example:
      ```typescript
      const behaviorSubject = new BehaviorSubject<number>(0);
      behaviorSubject.subscribe(value => console.log(value)); // Output: 0
      behaviorSubject.next(1); // Output: 1
      behaviorSubject.next(2); // Output: 2
      ```
    - `BehaviorSubject` is useful for representing state and sharing the latest value.
    - Use `BehaviorSubject` when you need to provide an initial value or always have the latest value.

100. **What is RxJS?**
    - A library for reactive programming using observables.
    - Provides tools for working with asynchronous and event-based data streams.
    - Example of an observable:
      ```typescript
      const observable = new Observable(subscriber => {
        subscriber.next('Hello');
        subscriber.next('World');
        subscriber.complete();
      });
      observable.subscribe(value => console.log(value)); // Output: Hello, World
      ```
    - Common operators include `map`, `filter`, `mergeMap`, `switchMap`, etc.
    - Facilitates composing and transforming asynchronous data flows.

101. **How do you use custom pipes in Angular components?**
    - Define a custom pipe with the `@Pipe` decorator.
    - Example:
      ```typescript
      @Pipe({name: 'capitalize'})
      export class CapitalizePipe implements PipeTransform {
        transform(value: string): string {
          return value.charAt(0).toUpperCase() + value.slice(1);
        }
      }
      ```
    - Register the pipe in an Angular module.
    - Use the custom pipe in templates:
      ```html
      <p>{{ 'hello' | capitalize }}</p> <!-- Output: Hello -->
      ```
    - Custom pipes enhance reusability and readability of transformation logic.

102. **What are forms in Angular?**
    - Mechanisms for handling user input and form validation.
    - Types:
      - Template-driven forms: Defined using directives in templates.
      - Reactive forms: Defined using model-driven approach in TypeScript.
    - Example of a reactive form:
      ```typescript
      this.form = this.fb.group({
        name: ['', Validators.required],
        age: ['', [Validators.required, Validators.min(18)]]
      });
      ```
    - Provides tools for form control management, validation, and data binding.
    - Facilitates building complex forms with dynamic and conditional validation.

103. **Explain the use of switchMap and forkJoin operators in RxJS.**
    - `switchMap`: Projects each source value to an observable and flattens the resulting observables, cancelling previous inner observables.
    - Example:
      ```typescript
      this.searchTerm$.pipe(
        switchMap(term => this.apiService.search(term))
      ).subscribe(result => console.log(result));
      ```
    - `forkJoin`: Combines multiple observables and emits the final value as an array when all observables complete.
    - Example:
      ```typescript
      forkJoin({
        user: this.apiService.getUser(),
        posts: this.apiService.getUserPosts()
      }).subscribe(result => {
        console.log(result.user);
        console.log(result.posts);
      });
      ```
    - `switchMap` is useful for handling dependent or sequential HTTP requests.
    - `forkJoin` is useful for executing multiple HTTP requests in parallel and processing results together.

104. **What is the difference between AOT (Ahead-of-Time) and JIT (Just-in-Time) compilation in Angular?**
    - AOT: Compiles Angular templates and components at build time.
      - Pros: Faster initial load, smaller bundle size, early error detection.
    - JIT: Compiles Angular templates and components at runtime in the browser.
      - Pros: More flexibility, no need for a separate build step for template compilation.
    - Example:
      ```bash
      ng build --aot // Enables AOT compilation
      ng serve // Uses JIT compilation
      ```
    - AOT is preferred for production builds due to performance benefits.
    - JIT is commonly used during development for faster build cycles and debugging.

105. **What is the purpose of ngFor trackBy in Angular?**
    - Optimizes performance by tracking items in a collection by a unique identifier.
    - Reduces the need for Angular to re-render the entire list when items change.
    - Example:
      ```html
      <div *ngFor="let item of items; trackBy: trackById">
        {{ item.name }}
      </div>
      ```
      ```typescript
      trackById(index: number, item: any): number {
        return item.id;
      }
      ```
    - Improves rendering performance for large lists and complex data structures.
    - Ensures efficient change detection by minimizing unnecessary DOM manipulations.

106. **What are validators in Angular reactive forms?**
    - Functions that perform synchronous or asynchronous validation on form controls.
    - Built-in validators include `Validators.required`, `Validators.minLength`, `Validators.maxLength`, `Validators.pattern`, etc.
    - Example:
      ```typescript
      this.form = this.fb.group({
        name: ['', Validators.required],
        email: ['', [Validators.required, Validators.email]],
        password: ['', [Validators.required, Validators.minLength(8)]]
      });
      ```
    - Custom validators can be created to handle complex validation logic.
    - Example of a custom validator:
      ```typescript
      import { AbstractControl, ValidatorFn } from '@angular/forms';
      export function forbiddenNameValidator(nameRe: RegExp): ValidatorFn {
        return (control: AbstractControl): {[key: string]: any} | null => {
          const forbidden = nameRe.test(control.value);
          return forbidden ? {'forbiddenName': {value: control.value}} : null;
        };
      }
      this.form = this.fb.group({
        username: ['', [Validators.required, forbiddenNameValidator(/admin/)]]
      });
      ```

107. **How do you handle form data binding in Angular?**
    - Use `FormControl` for individual form fields, `FormGroup` for groups of controls, and `FormArray` for arrays of controls.
    - Example of a reactive form:
      ```typescript
      this.form = this.fb.group({
        name: ['', Validators.required],
        email: ['', [Validators.required, Validators.email]],
        addresses: this.fb.array([this.createAddress()])
      });
      createAddress(): FormGroup {
        return this.fb.group({
          street: '',
          city: '',
          state: '',
          zip: ''
        });
      }
      addAddress(): void {
        this.addresses.push(this.createAddress());
      }
      ```
    - Use the `[(ngModel)]` directive for two-way data binding in template-driven forms.
    - Example:
      ```html
      <input [(ngModel)]="name" name="name" required>
      ```
    - Helps in synchronizing form data between the model and the view.

108. **What is the difference between template-driven forms and reactive forms in Angular?**
    - **Template-driven forms**:
      - Defined in the template using directives like `ngModel`.
      - Example:
        ```html
        <form #form="ngForm" (ngSubmit)="onSubmit(form)">
          <input type="text" ngModel name="name" required>
        </form>
        ```
      - Simpler for basic forms but less control over form state and validation.
    - **Reactive forms**:
      - Defined in the component class using `FormGroup` and `FormControl`.
      - Example:
        ```typescript
        this.form = this.fb.group({
          name: ['', Validators.required],
          email: ['', [Validators.required, Validators.email]]
        });
        ```
      - Provides more control and flexibility for complex forms and dynamic validation.
    - Reactive forms are preferred for larger, more complex forms requiring dynamic validation.

109. **How do you set the value of specific fields in a form in Angular?**
    - Use `setValue` to set the entire form or form group.
    - Example:
      ```typescript
      this.form.setValue({
        name: 'John Doe',
        email: 'john@example.com',
        address: {
          street: '123 Main St',
          city: 'Anytown'
        }
      });
      ```
    - Use `patchValue` to set specific fields or partial form.
    - Example:
      ```typescript
      this.form.patchValue({
        name: 'Jane Doe'
      });
      ```
    - Use `setValue` for complete value updates and `patchValue` for partial updates.
    - Ensures form controls are updated correctly and maintains form state.

110. **Explain host binding and host listener in Angular.**
    - **Host binding**: Binds a property to a host element property.
    - Example:
      ```typescript
      @Component({
        selector: 'app-example',
        template: '<p>Hello, world!</p>'
      })
      export class ExampleComponent {
        @HostBinding('class.active') isActive = true;
      }
      ```
    - **Host listener**: Listens to events on the host element.
    - Example:
      ```typescript
      @Component({
        selector: 'app-example',
        template: '<p>Click me!</p>'
      })
      export class ExampleComponent {
        @HostListener('click') onClick() {
          console.log('Element clicked');
        }
      }
      ```
    - Host binding and host listener simplify interaction with the host element.
    - Helps in encapsulating component logic and styles.

111. **Have you customized any Angular Material components, or have you created your own custom components using Angular Material?**
    - Yes, Angular Material components can be customized using theming and CSS overrides.
    - Example of theming:
      ```typescript
      @Component({
        selector: 'app-custom-button',
        template: '<button mat-button>Custom Button</button>',
        styleUrls: ['./custom-button.component.scss']
      })
      export class CustomButtonComponent {}
      ```
    - Custom CSS can override default styles:
      ```scss
      .mat-button {
        background-color: #4CAF50;
        color: white;
      }
      ```
    - Create custom components using Angular Material:
      ```typescript
      @Component({
        selector: 'app-custom-dialog',
        template: '<h1 mat-dialog-title>Custom Dialog</h1>',
        styleUrls: ['./custom-dialog.component.scss']
      })
      export class CustomDialogComponent {}
      ```
    - Customization improves UI consistency and user experience.

112. **What is the benefit of using subject in Angular?**
    - Subjects are both observable and observer, allowing them to emit values to multiple subscribers.
    - Example:
      ```typescript
      const subject = new Subject<string>();
      subject.subscribe(value => console.log(`Observer 1: ${value}`));
      subject.subscribe(value => console.log(`Observer 2: ${value}`));
      subject.next('Hello'); // Output: Observer 1: Hello, Observer 2: Hello
      ```
    - Subjects facilitate multicasting, enabling multiple subscribers to receive the same values.
    - Useful for implementing shared data streams and event buses.
    - Enhances inter-component communication and state management.

113. **What is the difference between reactive forms and template-driven forms in Angular?**
    - **Template-driven forms**:
      - Defined using directives in the template.
      - Simpler and less code for basic forms.
      - Example:
        ```html
        <form #form="ngForm" (ngSubmit)="onSubmit(form)">
          <input type="text" ngModel name="name" required>
        </form>
        ```
      - Suitable for simple use cases with minimal validation logic.
    - **Reactive forms**:
      - Defined using `FormGroup`, `FormControl`, and `FormBuilder` in the component.
      - Provides more control and flexibility for complex forms.
      - Example:
        ```typescript
        this.form = this.fb.group({
          name: ['', Validators.required],
          email: ['', [Validators.required, Validators.email]]
        });
        ```
      - Ideal for complex scenarios requiring dynamic validation and advanced form control.
    - Reactive forms are generally preferred for larger applications due to better control and testability.

114. **What is an Angular interceptor, and how is it used?**
    - Interceptors intercept and handle HTTP requests and responses.
    - Used for logging, authentication, caching, and modifying requests/responses.
    - Example:
      ```typescript
      @Injectable()
      export class AuthInterceptor implements HttpInterceptor {
        intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {
          const clonedRequest = req.clone({
            headers: req.headers.set('Authorization', 'Bearer token')
          });
          return next.handle(clonedRequest);
        }
      }
      ```
    - Provide interceptors in the Angular module:
      ```typescript
      @NgModule({
        providers: [
          { provide: HTTP_INTERCEPTORS, useClass: AuthInterceptor, multi: true }
        ]
      })
      ```
    - Interceptors enable centralized and reusable HTTP handling logic.

115. **Explain the difference between NG build and NG serve and what is the difference between "ng serve" and "npm start"?**
    - **ng build**:
      - Compiles the application into an output directory.
      - Produces optimized bundles for production.
      - Example:
        ```bash
        ng build --prod
        ```
    - **ng serve**:
      - Serves the application locally with live reload.
      - Uses JIT compilation for faster development cycles.
      - Example:
        ```bash
        ng serve
        ```
    - **npm start**:
      - Runs the `start` script defined in `package.json`.
      - Usually configured to run `ng serve`.
      - Example:
        ```json
        "scripts": {
          "start": "ng serve"
        }
        ```
    - `ng build` is for production builds, while `ng serve` is for local development with live reload.
    - `npm start` typically runs `ng serve` but can be customized for other tasks.

116. **Why did Angular switch from AngularJS to TypeScript?**
    - TypeScript offers static typing, which improves code quality and maintainability.
    - Enhanced tooling support, including better autocompletion, refactoring, and debugging.
    - TypeScript's features like classes, interfaces, and generics align with Angular's component-based architecture.
    - Improved developer productivity with better error detection at compile time.
    - Easier to adopt modern JavaScript features and syntax, ensuring future compatibility.

117. **Can you explain the Angular lifecycle methods?**
    - **ngOnInit**: Called once after the first `ngOnChanges` and initializes the component.
    - **ngOnChanges**: Called when input properties change.
    - **ngDoCheck**: Custom change detection logic can be implemented here.
    - **ngAfterContentInit**: Called once after the content projection is initialized.
    - **ngAfterContentChecked**: Called after each check of projected content.
    - **ngAfterViewInit**: Called once after the component's view and child views are initialized.
    - **ngAfterViewChecked**: Called after each check of the component's view and child views.
    - **ngOnDestroy**: Cleanup logic before the component is destroyed.

118. **What is the difference between ngDoCheck and ngOnChanges?**
    - **ngOnChanges**:
      - Called before `ngOnInit` and whenever input properties change.
      - Receives a `SimpleChanges` object containing the current and previous values.
      - Example:
        ```typescript
        ngOnChanges(changes: SimpleChanges) {
          console.log(changes);
        }
        ```
    - **ngDoCheck**:
      - Called with every change detection run.
      - Allows custom change detection logic.
      - Example:
        ```typescript
        ngDoCheck() {
          console.log('Custom change detection logic');
        }
        ```
    - **ngOnChanges** is triggered by input property changes, while **ngDoCheck** is triggered by any change detection cycle.

119. **How do you handle errors in a centralized manner in Angular?**
    - Use Angular's global error handler by extending `ErrorHandler`.
    - Example:
      ```typescript
      @Injectable()
      export class GlobalErrorHandler implements ErrorHandler {
        handleError(error: any): void {
          // Custom error handling logic
          console.error('An error occurred:', error);
        }
      }
      ```
    - Provide the custom error handler in the Angular module:
      ```typescript
      @NgModule({
        providers: [
          { provide: ErrorHandler, useClass: GlobalErrorHandler }
        ]
      })
      ```
    - Use HTTP interceptors for handling HTTP errors.
    - Example:
      ```typescript
      @Injectable()
      export class HttpErrorInterceptor implements HttpInterceptor {
        intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {
          return next.handle(req).pipe(
            catchError((error: HttpErrorResponse) => {
              // Custom HTTP error handling logic
              return throwError(error);
            })
          );
        }
      }
      ```
    - Centralized error handling improves maintainability and consistency.

120. **Explain currying with an example.**
    - Currying transforms a function with multiple arguments into a sequence of functions, each with a single argument.
    - Example:
      ```typescript
      function add(a: number) {
        return function(b: number) {
          return a + b;
        };
      }
      const add5 = add(5);
      console.log(add5(3)); // Output: 8
      ```
    - Curried functions allow partial application of arguments.
    - Example:
      ```typescript
      function multiply(a: number) {
        return function(b: number) {
          return a * b;
        };
      }
      const double = multiply(2);
      console.log(double(4)); // Output: 8
      ```
    - Currying enhances reusability and modularity of functions.

121. **How would you inject a dynamic script into an Angular application without using any built-in functions?**
    - Create a service to dynamically load scripts.
    - Example:
      ```typescript
      @Injectable()
      export class ScriptService {
        loadScript(url: string): Promise<void> {
          return new Promise((resolve, reject) => {
            const script = document.createElement('script');
            script.src = url;
            script.onload = () => resolve();
            script.onerror = () => reject();
            document.head.appendChild(script);
          });
        }
      }
      ```
    - Use the service in a component to load the script.
    - Example:
      ```typescript
      constructor(private scriptService: ScriptService) {}
      ngOnInit() {
        this.scriptService.loadScript('https://example.com/script.js')
          .then(() => console.log('Script loaded successfully'))
          .catch(() => console.error('Script loading failed'));
      }
      ```
    - Dynamic script loading enhances flexibility and allows integration of third-party libraries.

122. **How do you conditionally apply classes in Angular templates?**
    - Use `[ngClass]` directive for conditional class application.
    - Example:
      ```html
      <div [ngClass]="{'active': isActive, 'disabled': isDisabled}">
        Conditionally styled div
      </div>
      ```
    - Apply classes based on component properties.
    - Example:
      ```typescript
      isActive = true;
      isDisabled = false;
      ```
    - Use ternary operators for simpler conditions.
    - Example:
      ```html
      <div [ngClass]="isActive ? 'active' : 'inactive'">
        Conditionally styled div
      </div>
      ```
    - Enhances dynamic styling based on application state.

123. **How to upgrade Angular applications?**
    - Use Angular CLI for version updates.
    - Example:
      ```bash
      ng update @angular/cli @angular/core
      ```
    - Follow Angular's official upgrade guide for detailed steps.
    - Review breaking changes and update code accordingly.
    - Update third-party dependencies to compatible versions.
    - Test the application thoroughly after the upgrade to ensure stability.

124. **What is a model in Angular?**
    - A model represents the data structure used in an application.
    - Defined using TypeScript interfaces or classes.
    - Example:
      ```typescript
      export interface User {
        id: number;
        name: string;
        email: string;
      }
      ```
    - Models facilitate type-checking and data consistency.
    - Used to define the shape of data exchanged between components and services.
    - Enhances maintainability and readability of the codebase.

125. **What are forms in Angular?**
    - Forms in Angular are used to capture and validate user input.
    - Angular supports both template-driven forms and reactive forms.
    - Template-driven forms rely on directives like `ngModel` for two-way data binding.
    - Reactive forms are defined programmatically using `FormGroup`, `FormControl`, and `FormBuilder`.
    - Forms handle user interaction and data submission in Angular applications.

126. **What is a template-driven form?**
    - Template-driven forms in Angular are created and manipulated in the HTML template.
    - Uses directives like `ngModel`, `ngModelGroup`, and `ngForm` for form creation and validation.
    - Example:
      ```html
      <form #f="ngForm" (ngSubmit)="onSubmit(f)">
        <input type="text" name="username" ngModel required>
        <button type="submit">Submit</button>
      </form>
      ```
    - Suitable for simpler forms with less complex validation logic.
    - Provides automatic synchronization between form controls and model state.

127. **What are reactive forms?**
    - Reactive forms in Angular are created programmatically in the component class.
    - Uses `FormGroup`, `FormControl`, and `FormBuilder` for form creation and validation.
    - Example:
      ```typescript
      this.form = this.fb.group({
        username: ['', Validators.required],
        email: ['', [Validators.required, Validators.email]]
      });
      ```
    - Provides more control and flexibility for complex forms and dynamic validation logic.
    - Offers better scalability and testability compared to template-driven forms.

128. **What is a form group, form control, and form array?**
    - **FormGroup**: Represents a group of form controls. Used to manage the state of a group of related form controls.
      ```typescript
      this.form = this.fb.group({
        username: '',
        password: ''
      });
      ```
    - **FormControl**: Represents an individual form control, such as an input field. Used to manage the value and validation state of the form control.
      ```typescript
      this.username = new FormControl('', Validators.required);
      ```
    - **FormArray**: Represents an array of form controls. Used when dealing with dynamic lists of form controls.
      ```typescript
      this.addresses = this.fb.array([
        this.fb.group({ street: '', city: '' }),
        this.fb.group({ street: '', city: '' })
      ]);
      ```

129. **What is Form Builder?**
    - `FormBuilder` is a helper service provided by Angular for simplifying the creation of `FormGroup` and `FormControl` instances.
    - Example usage with `FormBuilder`:
      ```typescript
      constructor(private fb: FormBuilder) {}
      
      ngOnInit() {
        this.form = this.fb.group({
          username: ['', Validators.required],
          email: ['', [Validators.required, Validators.email]]
        });
      }
      ```
    - Encapsulates common form-building patterns and reduces boilerplate code.
    - Improves readability and maintainability of form-related code.

130. **What is validators class in reactive forms?**
    - Validators in reactive forms are functions used to validate form control values.
    - Angular provides built-in validators like `Validators.required`, `Validators.minLength`, `Validators.maxLength`, and `Validators.pattern`.
    - Example usage:
      ```typescript
      this.form = this.fb.group({
        username: ['', Validators.required],
        email: ['', [Validators.required, Validators.email]]
      });
      ```
    - Custom validators can also be defined to handle specific validation requirements.
    - Validators ensure data integrity and enforce validation rules on form inputs.

131. **What are strong typed forms?**
    - Strong typed forms in Angular refer to using TypeScript types/interfaces to define the structure and types of form data.
    - Example:
      ```typescript
      interface User {
        username: string;
        email: string;
      }

      this.userForm = this.fb.group({
        username: ['', Validators.required],
        email: ['', [Validators.required, Validators.email]]
      } as FormGroup);
      ```
    - TypeScript types ensure type safety and provide auto-completion and type-checking benefits during development.
    - Helps catch potential errors at compile-time rather than runtime.

132. **How to get values in disabled reactive forms?**
    - Use the `value` property of `FormControl` or `FormGroup` to access the current value, even if the control is disabled.
    - Example:
      ```typescript
      console.log(this.userForm.get('username').value);
      ```
    - Directly accessing `value` allows retrieving form data regardless of the form control's disabled state.
    - Useful for displaying or processing form data that users cannot modify.

133. **What are the state management options available in Angular?**
    - **Services**: Use services to manage and share state between components.
    - **RxJS**: Utilize observables and subjects for reactive state management.
    - **ngrx/store**: Implement Redux-like state management with actions, reducers, and selectors.
    - **Behavioral subjects**: Share state across components using RxJS subjects like `BehaviorSubject` or `ReplaySubject`.

134. **What are some features of Angular 16?**
    - Angular 16 features include improved performance optimizations.
    - Enhanced CLI capabilities with new commands and configurations.
    - Updated Angular Material components with new features and improvements.
    - Support for TypeScript 4.x versions and ECMAScript standards.

135. **How does application bootstrapping work in Angular 16?**
    - Application bootstrapping in Angular 16 initializes the root module of the application.
    - The process begins with the `main.ts` file where the Angular application is bootstrapped using the `platformBrowserDynamic().bootstrapModule()` function.
    - Angular's bootstrap process loads the root module, its dependencies, and initializes the application's component tree.
    - Bootstrapping typically starts with the root component defined in the `AppModule`.

136. **What are the different ways to create a form in Angular?**
    - **Template-driven forms**: Created and controlled in the HTML template using directives like `ngModel`.
    - **Reactive forms**: Created programmatically in the component class using `FormBuilder`, `FormGroup`, `FormControl`, and `FormArray`.
    - Both approaches provide different levels of control and flexibility based on application requirements and developer preferences.

137. **Explain the difference between reactive forms and template-driven forms in Angular.**
    - **Template-driven forms**:
      - Relies on directives within the HTML template (`ngModel`, `ngForm`).
      - Simplifies form creation with minimal TypeScript code.
      - Two-way data binding between form controls and model data.
      - Suitable for simpler forms and quick development iterations.

    - **Reactive forms**:
      - Created programmatically in the component class using TypeScript (`FormBuilder`, `FormGroup`, `FormControl`, `FormArray`).
      - Offers more control and flexibility for complex forms and validation logic.
      - Provides a reactive approach with observable data streams.
      - Better suited for large-scale applications and forms requiring dynamic behavior and validation.

138. **How do you set the value of specific fields in a form in Angular?**
    - Use the `setValue()` or `patchValue()` methods of `FormControl` or `FormGroup` to set values programmatically.
    - **setValue()**: Sets the value of all form controls in the group.
      ```typescript
      this.userForm.setValue({
        username: 'john_doe',
        email: 'john@example.com'
      });
      ```
    - **patchValue()**: Sets the value of specific form controls without affecting others.
      ```typescript
      this.userForm.patchValue({
        username: 'john_doe'
      });
      ```
    - Ensure the values passed comply with form control validators and data types.

139. **Explain host binding and host listener in Angular.**
    - **Host binding (`@HostBinding`)**: Binds a directive property to a host element's property or attribute.
      ```typescript
      @HostBinding('style.backgroundColor') backgroundColor: string = 'yellow';
      ```
      - Updates the host element's style dynamically based on component data.

    - **Host listener (`@HostListener`)**: Listens to events on the host element.
      ```typescript
      @HostListener('mouseenter') onMouseEnter() {
        this.highlight('yellow');
      }
      ```
      - Executes component methods in response to host element events.

    - Both decorators enhance component-directive interaction and enable dynamic behavior based on host element events and properties.

Certainly! Let's proceed with the next set of questions:

140. **How do you handle form data binding in Angular?**
    - Angular supports two-way data binding for form controls using `ngModel` in template-driven forms.
    - Example:
      ```html
      <input type="text" [(ngModel)]="username">
      ```
    - For reactive forms, use `formControlName` directive in conjunction with `FormGroup` and `FormControl`.
    - Example:
      ```html
      <input type="text" formControlName="username">
      ```
    - Data binding synchronizes input values with component properties and vice versa, ensuring real-time updates between the view and model.

141. **Can you explain the patchValue and setValue methods in Angular forms?**
    - **setValue()**: Sets the value of all form controls in a `FormGroup`.
      ```typescript
      this.userForm.setValue({
        username: 'john_doe',
        email: 'john@example.com'
      });
      ```
      - Requires all form controls to be defined and provided values.

    - **patchValue()**: Sets the value of specific form controls in a `FormGroup`.
      ```typescript
      this.userForm.patchValue({
        username: 'john_doe'
      });
      ```
      - Allows setting values for selected form controls without affecting others.
      - Useful for partial updates or when not all form controls need to be set.

142. **What version of Angular are you currently working with?**
    - As of my last update, Angular 17 is the latest version available.
    - Angular versions may have updated since then, so it's recommended to check the official Angular website or documentation for the most current version.

143. **Have you used Firebase in your Angular projects? If so, how?**
    - Yes, Firebase is commonly used with Angular for backend services, authentication, real-time databases, and hosting.
    - Integration involves installing Firebase SDK, configuring Firebase credentials, and using AngularFire library for Angular-specific bindings.
    - Example:
      ```typescript
      import { AngularFireModule } from '@angular/fire';
      import { AngularFirestoreModule } from '@angular/fire/firestore';

      const firebaseConfig = {
        apiKey: 'YOUR_API_KEY',
        authDomain: 'YOUR_AUTH_DOMAIN',
        projectId: 'YOUR_PROJECT_ID',
        storageBucket: 'YOUR_STORAGE_BUCKET',
        messagingSenderId: 'YOUR_MESSAGING_SENDER_ID',
        appId: 'YOUR_APP_ID'
      };

      @NgModule({
        imports: [
          AngularFireModule.initializeApp(firebaseConfig),
          AngularFirestoreModule
        ]
      })
      export class AppModule { }
      ```
    - AngularFire simplifies Firebase integration with Angular components and services.

144. **Explain the difference between template-driven forms and reactive forms in Angular.**
    - **Template-driven forms**:
      - Relies on directives within the HTML template (`ngModel`, `ngForm`).
      - Two-way data binding between form controls and model.
      - Easier to set up for simpler forms with less validation logic.
      - Minimal TypeScript code required.

    - **Reactive forms**:
      - Created programmatically using TypeScript (`FormGroup`, `FormControl`, `FormBuilder`).
      - Reactive approach with observable data streams.
      - Provides more control and flexibility for complex forms and validation.
      - Better suited for larger applications and dynamic form requirements.

145. **Have you worked with serverless Angular applications? If so, how?**
    - Yes, serverless Angular applications are deployed as static assets to cloud services like AWS S3, Firebase Hosting, or Netlify.
    - Angular applications interact with backend services via APIs, often hosted on serverless platforms like AWS Lambda, Azure Functions, or Firebase Cloud Functions.
    - Serverless architectures reduce operational overhead and scale automatically based on demand.
    - Example:
      - Deploying an Angular application to Firebase Hosting:
        ```bash
        ng build --prod
        firebase deploy
        ```
    - Serverless architectures are cost-effective and suitable for many types of web applications.

146. **What are some techniques for optimizing Angular applications for SEO?**
    - Use Angular Universal for server-side rendering (SSR) to pre-render pages on the server.
    - Implement meta tags and structured data for search engines using Angular's `Meta` service.
    - Ensure content is accessible without JavaScript enabled (progressive enhancement).
    - Optimize performance with lazy loading, code splitting, and efficient data fetching strategies.
    - Monitor and improve page load times and mobile responsiveness.

147. **Can you discuss the concept of push notifications in Firebase for Angular applications?**
    - Firebase Cloud Messaging (FCM) enables push notifications for Angular applications.
    - Integrates with Firebase backend to send notifications to clients on web, iOS, and Android devices.
    - Example:
      ```typescript
      import { AngularFireMessaging } from '@angular/fire/messaging';

      constructor(private afMessaging: AngularFireMessaging) {}

      requestPermission() {
        this.afMessaging.requestToken.subscribe(
          (token) => {
            // Send token to server for targeting notifications
          },
          (error) => {
            console.error('Unable to get permission to notify.', error);
          }
        );
      }
      ```
    - Enables real-time engagement with users through targeted notifications.
