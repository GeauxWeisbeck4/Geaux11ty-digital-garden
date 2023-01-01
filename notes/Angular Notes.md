- # Table of Contents
    - i. [[Firebase.io Angular Project]]
    - ii. [[Angular Basics]]
    - iii. [[Angular Codecademy]]
    - 
- 
- 
- # Angular Basics
    - ## Components
        - ### Decorators
            - Have three parts:
                - Selector: HTML Tag
                - templateUrl: Path to HTML file
                - styleUrls: Path to CSS file
            - ```javascript
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})```
                - We can find the `app-root` selector being used in `index.html`
        - ### app.component.html
            - The template that is used by Angular
