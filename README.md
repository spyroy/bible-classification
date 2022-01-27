## the problem:
to classify a sentance into a book in the bible.

for example:

"In the beginning God created the heaven and the earth"
the answer should be:

"Genesis"

at start we tried to solve simplier problem, instead classifying the sentance into book, we tried to classify it to old/new testament.

to do so we used linear regression which we think is the best option for this problem.

we got accuracy of - 0.86 which is not bad but can be improved, since this is not our original problem we were content with this result.

after that we tried to solve our problem using simple logistic regression.

after short time we realized that this model can't solve our problem because logistic regression is used to clasiify to binary values, but we have 66 different labels so that didn't work.

to make logistic regression work we decided to use softmax, which gives probability for every prediction label.

this model sounds like it can solve our problem but the result we got were not so good.

it seems that our data is more complicated than we thought, and this model gave very close probability to every book.

after that we tried multilayer perceptron neural network model.

we tried at first 2 hidden layers with size 100,50

but we got vanishing gradient.

so we tried 3 hidden layers with size 50,25,12

but it took too many time to train and the learning rate was to low.

and finally we tried with only 1 hidden layer with size 50 which worked pretty well, but the problem was we gave all the data as train set and it took a lot of time, to fix this we simply divided the train set and the test set to 80% 20% and finally we got good result.

after we realized that we changed all our model with the same train and test set.

process of work:
the start of every stage was similar, first we read the data than we tokenized the vocabulary and converted every verse into vector of the words that apears in the verse.

for example: "In the beginning God created the heaven and the earth" -> [1,3,1,1,1,1,1,0,0,0,0...]

"in" apears one time, "the" apears 3 time and so on.

after that we made every book to one hot encoded vector.

for example: Genesis -> [1,0,0,0,0...]

than for every model we gave the right weights, bias and function (sigmoid, relu) and trained the set.

somtimes the train set was all the data and somtimes we took 200 random verses from the data.
 
