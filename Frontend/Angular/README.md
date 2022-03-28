# Use of FormArrays:
```
.ts file

constructor(private fb: FormBuilder){}
...
ngOnInit() {
  ...
  this.from = this.buildForm();
  ...
}
...
private buildForm() {
  const arrayModel: FormBuilderType<{arrayModel: {attribute1: number, attribute2: number}}>{
      arrayModelDetails: this.fb.group({
          attrbute1: this.fb.control(null),
          attribute2: this.fb.control(null)
        })
  }
  
  const formModel: FormBuilderType<{model: {attribute1: number, attrbute2: {arrayModel: {attribute1: number, attribute2: number}}}> {
      formModelDetails: this.fb.group({
        attribute1: this.fb.control(null, Validators.required),
        attribute2: this.fb.array([arrayModel.arrayModelDetails])
      })
  }
  
  return this.fb.group(formModel);
}
```
```
.html template

<div [formGroup]="form">
  <ion-grid formGroupName="formModelDetails">
    <ion-card>
      <ion-row>
        <ion-col>
          <input formControlName="attribute1">
        </ion-col>
      </ion-row>
      <ng-container fomrArrayName="attribute2">
        <ion-row *ngFor="let _ of arrayModelDetails?.controls; let i=index" [formGroupName]="i">
          <ng-container>
            <ion-col>
              <input formControlName="attribute1">
            </ion-col>
            <ion-col>
              <input formControlName="attribute2">
            </ion-col>
          </ng-container>
        </ion-row>
      </ng-container>
    </ion-card>
  </ion-grid>
</div>
```
