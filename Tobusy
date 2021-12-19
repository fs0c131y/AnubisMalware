let toBusy = v =>
  switch v {
  | Init => Loading              
  | Loading as a => a 
  | Loading rescript as a => a           
  | Reloading(_) as a => a
  | Complete(a) => Reloading(a)
}
