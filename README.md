#创建列表
 (a_list <- list (
    c(1,24,5,7,8),
    letters[1:5],
    month.abb,
    asin
    matrix(c(2,3,45,7),nrow=2)
))


#使用names命名

name(a_list) <-c("catalan","letters","month","arcsin","involutaruy")

##嵌套
(main_list <- (
  middle_list <- (
    elegent_in_middle_list = diag(3),
    inner_list = list(
    elegent_in_inner_list = pi ^ (1:4)
    another_ elegent_in_inner_list  = "a"
   )
),
elegent_in_main_list = lod10(1:10)
))

#原子变量与递归变量
##是否是原子变量
is.atomic(list())
is.atomic(numeric())

##是否是递归变量
is.recursive(list())
is.recursive(numeric())

#列表的维度
length(a_list)
length(main_list)
dim(a_list)
nrow(a_list)
NROW(a_list)
NCOL(a_list)

#列表的算术运算
l1 <- list(2:6)
l2 <- list(7:11)
l1 [[1]] +l2 [[1]]




#索引列表
l <-  list(
  first = 1
  second = 2
  third = list(
    alpha = 3.1
    beta = 3.2
  )
)

##创建一个列表
l <- list(first = 1, second = 2.third = list(alpha = 3.1,beta = 3.2))
l[1:2]
l[-3]
l[c(TRUE,TRUE,FALSE)]
l[[1]]
l[["first"]]

is.list(l[1])
is.list(l[[1]])

l$first
l$f

l[["third"]]["beta"]
l[["third"]][["beta"]]
l[["c(third","beta")]]
is.list(l[["third"]]["beta"])
is.list(l[["third"]][["beta"]])

l[c(4,2,5)]
l[c("fourth","second","fifth")]

l[["fourth"]]
1$fourth
l[[4]]

#向量和列表之间的转换
busy_beaver <- c(2,45,676,889)
as.list(busy_beaver)

as.numeric(list(2,45,676,889))

##列表中含有非标量元素
（prime_factor <- list(
  two = 2,
  three = 3,
  four = c(2,32),
  five = 5 ,
  six = c(2,3),
  seven = 7,
  eight = c(2,3,4),
  nine = 9,
  ten = c(2,5)
  ))

##unlist函数
new_factors <- unlist(prime_factors)
new_factors 

#组合列表
c(list(a=1,b=2),list(3))

##cbind()和rbind()
matrix_list_hybrid <- cbind(list(a=1,b=2),list(c=3,list(d=4))
matrix_list_hybrid
str(matrix_list_hybrid)

#NULL
china_holiday <- list(
     Jan  =  "New Year’s Day",
     Feb = "Spring Festival",
     Mar = NULL
     Apr = "Qingming Festival",
     May = "May Day",
     Jun = "Dragon Boat Festival",
     Jul = NULL,
     Aug = NULL,
     Sep = "Moon Festival",
     Oct = "National Day",
     Nov = NULL,
     Dec = NULL
  )

length(NULL)
length(NA)
is.null(NULL)
is.null(NA)
is.na(NULL)

china_holiday$Sep <- NULL
china_holiday 

china_holiday $Jun <- list(NULL)
china_holiday 

#成对列表
(arguments_of_sd <- formals(sd))
class( arguments_of_sd)

pairlist()
list()


#数据框
##创建数据框
(a_data_frame <- data.frame(
  x = letters[1:5],
  y = rnorm(5),
  z = runif(5)>0.5,
))

class(a_data_frame )


y <- rnorm(5)
names(y) <- month.name[1:5]
data.frame(
  x = letters[1:5],
  y=y,
  z= runif(5)>0.5,
)


data.frame(
  x = letters[1:5],
  y=y,
  z= runif(5)>0.5,
  row.names = NULL
)


data.frame(
  x = letters[1:5],
  y=y,
  z= runif(5)>0.5,
  row.names = c("Jackie","Tito","Jermaine","Marlon","Michael")
)

###colnames和dimnames
rownames(a_data_frame) 
colnames(a_data_frame) 
dimnames(a_data_frame) 
nrow(a_data_frame) 
ncol(a_data_frame) 
dim(a_data_frame) 

length(a_data_frame) 
names(a_data_frame) 


data.frame(
  x =1,
  y= 2:3,
  z = 4:7
)
data.frame(
  x =1,
  y= 2:3,
  z = 4:6
)

###check.names
data.frame(
  "A column" = letters[1:5],
  "..." =rnorm(5),
  "..." = runif(5) > 0.5,
  check.names = TRUE

data.frame(
  "A column" = letters[1:5],
  "..." =rnorm(5),
  "..." = runif(5) > 0.5,
  check.names = FALSE

#索引数据框
a_data_frame[2：3，-3]

a_data_frame[c(FALSE,TRUE,TRUE,FALSE,FALSE),c("x","y")]

a_data_frame[2：3，1]

class(a_data_frame[2：3，-3])
class(a_data_frame[2：3，1])

a_data_frame$x[2：3]
a_data_frame$x[[1]][2：3]
a_data_frame[["x"]][2：3]

a_data_frame[a_data_frame$y>0|a_data_frame$z,"x"]
xubset(a_data_frame,y>0|z,x)

#基本数据框操作
t( a_data_frame)
class(t( a_data_frame))
another_ data_frame <-  data_frame(
  z = rlnorm(5),
  y = sample(5),
  x = letters[3:7]
)
rbind( a_data_frame,another_ data_frame)
cbind( a_data_frame,another_ data_frame)
merge( a_data_frame,another_ data_frame,by = "x")
merge( a_data_frame,another_ data_frame,by = "x",all= TRUE)
colSums( a_data_frame[,2：3])
colMeans( a_data_frame[,2：3])
#问题
Q1：以下列表的长度为多少？
A1：2

Q2：你会在哪里找到成对列表？
A2:成对列表仅在内部使用，用于将参数传递到函数中。

Q3：尽可能多地说出几种创建数据框子集的方法。
A3：1.使用subset()函数，它需要三个参数：数据框，行的条件逻辑向量，需要保留的名字向量。（如果最后一个参数被省略了，将保留所有列）
2.使用列表样式的索引，以下三种方式都将选择第一列中的第2、3个元素
 1)a_data_frame$x[2:3]
 2)a_data_frame[[1]][2:3]
 3)a_data_frame[[“列名”]][2:3]
3.使用四种不同的向量（正整数、负整数，逻辑值，字符）索引

Q4：如何创建一个数据框，使得它的列名既非唯一又非有效？
A4:通过给data.frame传入check.names = FALSE关闭该功能。

Q5：你会使用哪个函数将一个数据框追加到另一个之后？
A5：rbind或cbind

#练习
1.
 (a_list <- list (c(0,1,4,9),c(16),c (25),c(36),c(49), NULL,c(64),NULL,c (81),NULL))
names(a_list) <-c("0~9 ","10~19 ","20~29 ","30~39 ","40~49 ","50~59 ","60~69 ","70~79 ","80~89 ","90~99 ")
a_list

2.
a_data_frame <- data.frame(iris)
  colMeans(a_data_frame [,1:4])

3.
new_beaver1 =data.frame(id=1,beaver1)
new_beaver2 =data.frame(id=1,beaver2)
new_beaver = rbind(new_beaver1,new_beaver2)
#不是很懂什么叫作活跃着的海狸的子集·····		


#06
#环境
an_environment <- new.env()
an_environment 

#向环境中分配变量
an_environment[["pythag"]] <- c(21,334,55,78)
an_environment$root <- polyroot(c(2,-5,7))

##assign
assign(
  "Monday",
  weekdays(as.Date("1969/07/02")),
  an_environment
)

##get
an_environment[["pythag"]]
an_environment$root
get("Monday", an_environment)

ls(envir =  an_environment)
ls.str( envir = an_environment)

##exists
exists("pythag", an_environment)

#列表与环境之间变换
(a_list <- as.list (an_environment))

as.environment(a_list)
list2env(a_list)

#父环境与子环境
nested_environment <- new.env(parent =  an_environment)
exists("pythag",nested_ environment)
exists("pythag",nested_ environment,inherits = FALSE)

#访问全局和基础环境
non_strormers <<- c(2,3,5,6,7,8,9)
get("non_strormers ",envir = globalenv())
head(ls( envir = baseenv()),20)

#创建自定义函数
hypotenuse <- function(x,y){
   sqrt(x^2+y^2)
}
hypotenuse(3,4)
hypotenuse(x=24,y=7)




hypotenuse<- function(x=5,y=12){
   sqrt(x^2+y^2)
}
hypotenuse()

#检测函数
formals(hypotenuse)
args(hypotenuse)
formalArgs(hypotenuse)

(body_of_hypotenuse <- body(hypotenuse))
depare(body_of_hypotenuse )

#默认值常数值及形参
normalize <- function(x,m=mean(x),s=sd(x)){
    (x-m)/s
}
normalized <- normalize(c(1,3,6,10,15))
mean(normalized)
sd(normalized)

#默认值形参
normalize <- function(x,m=mean(x,na.rm = na.rm),s=sd(x,na.rm =na.rm),na.rm = FALSE){
   (x-m)/s
}
normalized <- normalize(c(1,3,6,10,NA))
normalized <- normalize(c(1,3,6,10,NA),na.rm = TRUE)

#默认值形参简化(…)
normalize <- function(x,m=mean(x,…),s=sd(x,…),...){
 (x-m)/s
}
normalized <- normalize(c(1,3,6,10,NA))
normalized <- normalize(c(1,3,6,10,NA),na.rm = TRUE)

#函数作为其他函数的参数
do.call(hypotenuse,list(x=3,y=4))

dfr1 <- data.frame(x = 1.5,y = rt(5,1))
dfr2 <- data.frame(x = 6:10,y = rt(5,1,1))
dfr3 <- data.frame(x = 11:15,y = rebeta(5,1,1))
do.call(rbind,list(dfr1,dfr2,dfr3))

menage <- c(1,0,0,1,2,13,80)
mean(menage)

mean(c(1,0,0,1,2,13,80))

x_plus_y <- function(x,y)x+y
do.call(x_plus_y,list(1:5,5:1))
do.call(function(x,y)x+y,ist(1:5,5:1))

#返回值为函数
emp_cun_dist_fn <- ecdf(rnorm(50))
is.function(emp_cun_dist_fn)

#变量的作用域
f  <- function(x9){
    y9 <- 1
    g <- function(y9)
      (x9+y9)/2
    }
    g(x9)
}
f(sqrt(5))


f  <- function(x8){
    y98<- 1
    g(x8)
}
g <- function(y8){
      (x8+y8)/2
}
    f(sqrt(5))


h <-function(x10){
    x10*y10
} 
h(9)
y10 <- 19
h(9)
y11 <- 19
h2 <- function(x11)
    if(runif(1)>0.5)y11 <- 12
    x11 * y11
    }

repllicate(10,h2(9))

#问题
Q1：全局环境的另一个名字是什么？
A1：全局变量

Q2：如何把列表转换为环境？
A2：使用as.environment()函数

Q3：如何将函数的内容打印到控制台上？
A3：1.直接输入函数名
2.使用body函数

Q4：列举三个能够输出函数形参名称的函数。
A4：formals，args，formalArgs

Q5：do.call函数能做什么？
A5：1.调用其他函数作为参数
    2.与rbind()函数配合，一次拼接多个数据框或矩阵


#练习
1.
multiples_of_pi<- new.env()
multiples_of_pi[["two_pi"]] <- 2*pi
multiples_of_pi$three_pi <-3*pi
assign(
  "four_pi",
  4*pi,
  multiples_of_pi
)
multiples_of_pi

2.
Pdjo <- function(x){
  y <- x/2
ifelse(is.finite(x), is.integer(y),NA)
}

Pdjo(6)
Pdjo(-5)
Pdjo(Inf)
Pdjo(0)
##不知如何排除0
 
3.
{f <-function(x,y) 
HS <- function(x,y){
a_list <- list(
formals (f),
"function(x,y)"
)
names(a_list) <- c("args","body")
return(a_list)
}
}
