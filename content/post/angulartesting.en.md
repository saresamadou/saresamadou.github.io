+++
author = "Samadou"
title = "Angular Testing"
date = "2022-09-10"
description = "Tdd with angular"
tags = [
    "testing",
]
+++


## Testing component


```typescript

describe('Component', () => {
  let component: ItemsComponent;
  let fixture: ComponentFixture<Component>;
  let debugElement: DebugElement;

  beforeEach(async () => {
    await TestBed.configureTestingModule({
      declarations: [ Component ]
    })
    .compileComponents();

    fixture = TestBed.createComponent(Component);
    component = fixture.componentInstance;
    debugElement = fixture.debugElement;

  });

  test('should create', () => {
    fixture.detectChanges();

    expect(component).toBeTruthy();
  });

  test('should list all items', () => {
    // Given
    const items = [ {id: 1, name: 'Tomato'}, {id: 2, name: 'Oignon'}, {id: 3, name: 'Salad'}];
    component.items$ = items;

    // When
    fixture.detectChanges();

    // Then
    const itemsPrinted = debugElement.nativeElement.querySelectorAll('.item');
    const pi = debugElement.queryAll(By.css('.item'));
    expect(itemsPrinted.length).toEqual(3);

  });
});
  
  it('should create the app', () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app).toBeTruthy();
  });

  it(`should have as title 'ng-fridge'`, () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app.title).toEqual('ng-fridge');
  });

  xit('should render title', () => {
    const fixture = TestBed.createComponent(AppComponent);
    fixture.detectChanges();
    const compiled = fixture.nativeElement as HTMLElement;
    expect(compiled.querySelector('.content span')?.textContent).toContain('ng-fridge app is running!');
  });
  
```
