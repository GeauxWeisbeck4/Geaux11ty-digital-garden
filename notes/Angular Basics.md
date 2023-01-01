- #[[Angular Notes]] for very basics
- to generate a component: `ng generate component name`
    - We can update this by changing `schematic` in `angular.json`
- Building forms
    - [formGroup]="habitForm" binds template to form
    - ```javascript
@Component({
  selector: 'app-habit-list',
  template: `
    <h2>Habits</h2>
    <form [formGroup]="habitForm" (ngSubmit)="onSubmit(habitForm.value)">
      <input type="text" placeholder="Add habit" formControlName="title" />
      <button type="submit">Add</button>
    </form>
    <ul>
      <app-habit-item
        *ngFor="let habit of habits"
        [habit]="habit"
      ></app-habit-item>
    </ul>
  `,
  styles: [],
})

export class HabitListComponent {
  habitForm;
  habits = [
    {
      id: 1,
      title: 'Check in with parents once a week',
    },
    {
      id: 2,
      title: 'Record 2 videos per day',
    },
    {
      id: 3,
      title: 'Work on side project 5 hours/week',
    },
    {
      id: 4,
      title: 'Write for 20 minutes a day',
    },
  ];

  constructor(private formBuilder: FormBuilder) {
    this.habitForm = this.formBuilder.group({
      // Pass in something into form
      title: '',
    });
  }

  onSubmit(newHabit) {
    const id = this.habits.length + 1;
    newHabit.id = id;
    this.habits.push(newHabit);
    this.habitForm.reset();
  }
}```
- # Generate a service
    - How we share data and business logic throughout an angular application
    - `ng generate service name` or `ng g s name`
        - add array and builider to service from component
            - ```javascript
// Our service
import { Injectable } from '@angular/core';
import { of, Observable } from 'rxjs';

@Injectable({
  providedIn: 'root',
})
export class HabitService {
  habits = [
    {
      id: 1,
      title: 'Check in with parents once a week',
    },
    {
      id: 2,
      title: 'Record 2 videos per day',
    },
    {
      id: 3,
      title: 'Work on side project 5 hours/week',
    },
    {
      id: 4,
      title: 'Write for 20 minutes a day',
    },
  ];

  constructor() {}

  getHabits(): Observable<any> {
    return of(this.habits);
  }

  addHabit(newHabit) {
    const id = this.habits.length + 1;
    newHabit.id = id;
    this.habits.push(newHabit);
  }
}
```
                - https://stackblitz.com/edit/egghead-angular-service-ym2bxa
                - Use async pipe to destroy subscription
                - set this.habits = observable
    - ## Add custom data types with typescript interfaces
        - `ng generate interface name` or `ng g i name`
        - https://stackblitz.com/edit/egghead-angular-interfaces-1hcgde
    - ## Add optional properties in Angular to typescript interfaces
        - https://stackblitz.com/edit/egghead-angular-optional-properties-zju6gq
    - ## Use Scoped Component Styles in Angular
        - [Egghead Angular Styling (forked) - StackBlitz](https://stackblitz.com/edit/egghead-angular-styling-dhmfxw?file=src%2Fapp%2Fhabit-form%2Fhabit-form.component.ts)
    - ## Add global styles to Angular
        - [Egghead Angular Styling (forked) - StackBlitz](https://stackblitz.com/edit/egghead-angular-styling-qecnbb?file=src%2Fstyles.css)
    - ## Use a proxy with the Angular CLI to fix CORS development problems
        - When we first try to use a local server for our data in development, we get a rude error in the console and nothing works. What is that and why are we getting it? Well, even though both the server and the client will eventually be on the same domain in production, we're getting CORS (cross-origin resource sharing) errors in development. That's because we're running the server and the client on different ports. We can fix this by setting up the Angular CLI to proxy all requests to the API for us so they appear to be coming from the same origin.
    - ## Refetching Data with subjects in Angular
        - One of the things that drove me crazy when I was first learning RxJS in Angular was how difficult it seemed to reload a collection of data after I added or deleted an item. With promises, I could just use .then() and be on my way. What do we do with observables? Should we just nest another subscription? Even if we do that, since we're using the async pipe, nothing will happen. There are better ways to handle this that are more reactive. In this lesson, I'm going to show you one way using Subjects. Subjects are kind of like event emitters that can have multiple listeners.
            - [samjulien/egghead-angular: Angular basics for egghead. (github.com)](https://github.com/samjulien/egghead-angular)
            - Use a subject -> uses multicasting (multiple listeners)
    - ## Add Routing to an existing Angular project
        - When we first create an Angular app with the Angular CLI using ng new, it gives us an option to add routing. Sometimes we don't know whether we want to add routing yet, so we say no. What do we do, though, if we decide to add routing later? There's no separate CLI command to set up the routing for you. In this lesson, I'll show you how to manually add routing to your Angular application.
            - `ng generate module app-routing --flat --module-app`
                - eh whatever do this instead
            - [Egghead Angular Routing (forked) - StackBlitz](https://stackblitz.com/edit/egghead-angular-routing-gfu2dw?file=src%2Fapp%2Fapp.module.ts)
    - ## Navigate between routes in Angular with routerLink
        - Once routing is set up, we can add a new route by adding a new component and adding a path to our routes array in app.module.ts. But how do we navigate between the two routes? In this lesson, I'll show you how to use routerLink to switch between the routes without causing the page to refresh.
            - https://stackblitz.com/edit/egghead-angular-router-link-5hcpuo?file=src%2Fapp%2Fapp.component.html
    - ## Navigate to and display components with route parameters in Angular
        - We often need to pass a parameter like an ID to a route and then access that ID in order to call an API to get some data. In this lesson, we'll look at how to define a route with a parameter, how to use params with the routerLink directive, and how to use the route snapshot to use a param in a component.
        - [Egghead Angular Route Params (forked) - StackBlitz](https://stackblitz.com/edit/egghead-angular-route-params-cnftu2?file=src%2Fapp%2Faccount-detail%2Faccount-detail.component.ts)
    - ## Subscribing to route params in Angular
        - There are two different ways to access route parameters in Angular components. One is through the route snapshot and the other is by subscribing to the route paramMap. When do you use each? In this lesson, we'll learn that trying to change and access a route parameter in the same component is the key to knowing when to subscribe to the paramMap instead of just using the snapshot.
        - Need to subscribe to an observable
        - https://stackblitz.com/edit/egghead-angular-route-params-subscribe?file=src%2Fapp%2Faccount-detail%2Faccount-detail.component.ts
    - ## Create Nested routes in Angular
        - Sometimes as our app grows in complexity we need to set up some nested routes (also known as child routes). We often want to do this so users can link to a deeper part of the app, which can't be done by just nesting a child component. In this lesson, you'll learn how to set up child routes in Angular.
            - [Angular Egghead Nested Routes (forked) - StackBlitz](https://stackblitz.com/edit/angular-egghead-nested-routes-jrmttd?file=src%2Fapp%2Fapp.module.ts)
    - ## Access parent route parameters in Angular
        - When we use child routes (also called nested routes), we often need to access a parent route's parameter, such as an ID used to make an API call. In this lesson, we'll learn how to subscribe to the parent route's paramMap in order to get that ID and use it in our child route component.
            - [Angular Egghead Access Parent Route Params (forked) - StackBlitz](https://stackblitz.com/edit/angular-egghead-access-parent-route-params-d7zkrx?file=src%2Fapp%2Fsystem-items%2Fsystem-items.component.ts)
    - ## Inherit parent route parameters by default with ParamsInheritanceStrategy
        - Right now, we're getting the ID route parameter off the of the parent route. This is because we want the info and items components to use the ID of the chosen camping system without having to pass it a second time. There's another way we can do this, though, and that's by defining a paramsInheritanceStrategy when we create our router module. The paramsInheritanceStrategy defines how the router merges parameters, data, and resolved data from parent to child routes. The default is "emptyOnly," which inherits those only for path-less or component-less routes. We're going to set it to "always" to enable unconditional inheritance of parent parameters, data, and resolved data in child routes.
        - 
