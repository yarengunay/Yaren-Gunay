# Yaren-Gunay
>  makeCacheMatrix<-function(m=matrix()) {
+ inv<-NULL
+ set<-function(matrix) {
+ m<<-matrix
+ inv<<-NULL
+ }
+ get<-function() m
+ getInverse<-function() inv
+ setInverse<-function(inverse) inv <<-inverse
+ list(set=set,get=get,getInverse=getInverse,setInverse=setInverse)
+ }
> 
> cacheSolve<-function(matrix) {
+ inv<-matrix$getInverse()
+ if(!is.null(inv)) {
+ message("Getting cached inverse")
+ return(inv)
+ }
+ mat<-matrix$get()
+ new_inv<-solve(mat)
+ matrix$setInverse(new_inv)
+ new_inv
+ }

