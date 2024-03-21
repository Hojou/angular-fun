# Cheat sheet

# MVP & Components

## Binding and interpolation
Property binding:
```html
<input [value]="myVariable">
```

Interpolation:
```html
<div>{{ myVariable }}</div>
```

Event binding:
```html
<input (click)="doStuff()">
```

## Templates
```html
@for (item of itemCollection) {
<div>{{ item.name }}</div>
}

@if (showMe) {
<div>Show this if showMe is true</div>
}
```

## Old templates syntax
```html
<div *ngFor="let item of itemCollection">{{ item.name }}</div>
<div *ngIf="showMe">Show this if showMe is true</div>
```

## Input
```typescript
@Input()
myParameter: SomeType;
```

## Reactive forms
Template:
```html
<input [formControl]="myInput">
```
Component:
```typescript
public myInput =  new FormControl('');

myInput.valueChanges.subscribe...
```


# Services, providers and DI

```typescript
constructor(service1: ServiceOne, private service2: ServiceTwo, public service3: ServiceThree) {
    // Access to all three services
}

someFunction() {
    // Access to service2 and service3
}

// service3 will be accessible in the html template as well as derived classes.
```

# Observables

```typescript
{{ observable$ | async | json }}

observable$.pipe(
    map(o => o.someNumberProperty),
    filter(n => n > 5),
    take(5)
).subscribe(number => {
    console.log('received a number', number)
});

const streamOfData$ = urlsToQuery$.pipe(
    flatMap(url => requestDataFrom(url)
));
```
Noteworthy: filter, map, merge, debounceTime, tap, switchMap


# Links
https://angular.io/

https://rxmarbles.com/

