
# OnlineFitBernoulli


````julia
using OnlineStats
using Distributions
````





### Create estimate with first batch
````julia
x = rand(Bernoulli(.3), 100)
obj = onlinefit(Bernoulli, x)
````





### Update model with many batches
````julia
for i = 1:10000
    x = rand(Bernoulli(.3), 100)
    update!(obj, x)
end
````





### Check fit
````julia
julia> state(obj)
3x2 Array{Any,2}:
 :p       0.300305
 :n       1.0001e6
 :nb  10001.0     

julia> mean(obj.d)
0.3003049695030497

````




