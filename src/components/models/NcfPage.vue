<script setup>
import NavContainer from '../NavContainer.vue';
import mlp from '@/assets/images/mlp.png'
import ncf_based from '@/assets/images/ncf_based.png'
const currentYear = new Date().getFullYear()
</script>


<template>
    <NavContainer/>
    <div class="body">
        <h1>NCF based Recommender</h1>
        <p>Neuronal Collaborative Filtering is an advanced recommendation system that leverages deep learning techniques to model complex user-item interactions. Unlike traditional 
            collaborative filtering methods that rely on matrix factorization or nearest neighbors, NCF uses neuronal networks to captura non linear relationships and high-order
            interactions between users and items. This approach allows for more accurate and personalized recommendations, especially in scenarios with complex and sparse data.
        </p>

        <img :src="mlp" class="mlp"/>

        <div>
            <p><b>How It Works</b></p>
            <p>The core principal behind NCF is using neuronal networks to capture user-item interactions, then compute the predictions. Here's how it operates: </p>
            <ul class="steps">
                <li>
                    <b>Input Representation: </b>
                    <ul>
                        <li>
                            <b>User Embeddings: </b> Each user is represented by a dense vector, often initialized randomly and learned through training.
                        </li>
                        <li>
                            <b>Item Embeddings: </b> Similarly, each item is represented by a dense vector, initialized and learned in the same manner as user embeddings.
                        </li>
                    </ul>
                </li>
                <li>
                    <b>Model Architecture: </b> 
                    <ul>
                        <li>
                            <b>Embedding Layers: </b> User and item embeddings are created through embedding layers that transform sparse user/item IDs into dense vectors.
                        </li>
                        <li>
                            <b>Interaction Layers: </b> The core of the NCF model involves combining user and item embeddings to capture their interactions. The architecture used is
                            <i>Multi-Layer-Perceptron (MLP)</i>, a series of fully connected layers that learn high-order interactions between users and items.
                            
                        </li>
                    </ul>
                </li>
                <li>
                    <b>Prediction: </b> The combined embeddings from MLP are passed through final dense layers to produce a prediction score, which represents the likelihood of a user
                    interactiong with an item.
                </li>
                <li>
                    <b>Training: </b> 
                    <ul>
                        <li>
                            <b>Loss Function: </b> The model is trained using a suitable loss function, tipically mean squared error (MSE) or huber loss for explicit
                            feedback, like ratings.
                        </li>
                        <li>
                            <b>Optimization: </b> The model is trained using stochastic gradient descent (SGD) or other optimization algorithms, such as Adam or Adagrad, and are
                            used to minimize the loss function and update the model parameters.
                        </li>
                    </ul>
                </li>
                <li>
                    <b>Recommendation Generation: </b> Once the model is trained, it can be used to generate recommendations for a given user. The recommendation is generated by
                    sorting the items based on their predicted scores and selecting the top-k items.
                </li>
                <li>
                    <b>Feedback Loop: </b> The system continuously updates its models based on new user interactions, improving the accuracy of recommendations over time.
                </li>
            </ul>
        </div>

        <img :src="ncf_based" class="ncf"/>

        <div>
            <p>This approach has several advantages: </p>
            <ul>
                <li>
                    <b>Modeling Complex Interactions: </b> NCF models can capture non-linear relationships and high-order interactions between users and items, which can be more accurate recommendations
                    compared to traditional collaborative filtering methods.
                </li>
                
                <li>
                    <b>Scalability: </b> NCF can handle large datasets and handle millions of users and items, making it scalable to large-scale applications.
                </li>

                <li>
                    <b>Improved Performance: </b> Opten outperforms traditional collaborative filtering techniques, especially in sparse datasets where traditional methods can struggle.
                </li>

            </ul>
        </div>
        
        <div>
            <p>However, there are some limitations to this approach: </p>
            <ul>
                <li>
                    <b>Computational Cost: </b> Training deep neuronal networks can be computationally expensive and time-consuming, requiring significant computational resources
                    and potentially long training times.
                </li>
                
                <li>
                    <b>Overfitting: </b> NCF models are prone to overfitting, especially when trained on small or noisy datasets. Regularization techniques, such as dropout, and careful
                    model validation are necessary to prevent overfitting.
                </li>

                <li>
                    <b>Complexity: </b> Designing and tuning neuronal network architectures involves many hyperparameters (e.g, number of layers, activation functions, learning rates),
                    which can be more complex and require extensive experimentation.
                </li>
            </ul>
        </div>

        <p>
           NCF represents a significant advancement in recommendation systems, offering the ability to model complex user-item interactions and deliver high personalized
           recommendations. While it brings considerable advantages in terms of accuracy and flexibility, it also poses challenges related to computational cost, overfitting, and model complexity.
           When applied effectively, NCF can significantly enhance the recommendation experience across various domains, making it a valuable tool for businesses and organizations.
        </p>
    </div>
    <div class="copyright">
        &copy; {{ currentYear }} Sunshine Movies. All rights reserved.
    </div>
</template>

<style scoped>
* {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.body {
    margin: 3% 3%;
    padding: 0 6.5%;
}

.copyright {
  padding: 2% 13%;
  background-color: rgba(250, 150, 50, 0.5)
}

h1 {
    color: rgba(250, 150, 50, 0.8)
}

p {
    text-align: justify;
    line-height: 1.5rem;
}

li {
  padding: 0.6rem 0;
  padding-right: 1.5rem;
  text-align: justify;
  line-height: 1.5rem;
}

.mlp {
    float: right;
    margin: 2rem 0rem;
    margin-left: 2rem;
    max-width: 50rem;
}

.steps {
    list-style: decimal;
}

.ncf {
    float: inline-start;
    width: 35rem;
    margin: 3rem 0;
    margin-inline-end: 3rem;
}

</style>