
# OnlineFitBeta


````julia
using OnlineStats
using Distributions
using Gadfly
````





### Create estimate with first batch
````julia
x = rand(Beta(3, 5), 100)
obj = onlinefit(Beta, x)
````





### Update model with many batches
````julia
for i = 1:10000
    x = rand(Beta(3, 5), 100)
    update!(obj, x)
end
````





### Check fit
````julia
julia> state(obj)
4x2 Array{Any,2}:
 :α       3.00042 
 :β       5.00149 
 :n       1.0001e6
 :nb  10001.0     

````




