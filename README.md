当然可以，以下是各个算法的公式：

算法	公式
梯度下降法	$w_{t+1}=w_t - \eta \cdot \nabla J(w_t)$
随机梯度下降法	$w_{t+1}=w_t - \eta \cdot \nabla J(w_t,x_i)$
批量梯度下降法	$w_{t+1}=w_t - \eta \cdot \frac{1}{n}\sum_{i=1}^n \nabla J(w_t,x_i)$
动量梯度下降法	$\begin{cases} v_t = \gamma v_{t-1} + \eta \nabla J(w_t) \ w_{t+1}=w_t - v_t \end{cases}$
AdaGrad	$\begin{cases} g_t = \nabla J(w_t) \ G_t = \sum_{i=1}^t g_i^2 \ w_{t+1} = w_t - \frac{\eta}{\sqrt{G_t+\epsilon}} \cdot g_t \end{cases}$
RMSprop	$\begin{cases} g_t = \nabla J(w_t) \ G_t = \gamma G_{t-1} + (1-\gamma) g_t^2 \ w_{t+1} = w_t - \frac{\eta}{\sqrt{G_t+\epsilon}} \cdot g_t \end{cases}$
Adam	$\begin{cases} m_t = \beta_1 m_{t-1} + (1-\beta_1) \nabla J(w_t) \ v_t = \beta_2 v_{t-1} + (1-\beta_2) (\nabla J(w_t))^2 \ \hat{m_t} = \frac{m_t}{1-\beta_1^t} \ \hat{v_t} = \frac{v_t}{1-\beta_2^t} \ w_{t+1} = w_t - \frac{\eta}{\sqrt{\hat{v_t}}+\epsilon} \hat{m_t} \end{cases}$
其中，$w_t$是第t次迭代时的权重参数，$\eta$是学习率，$J(w_t)$是损失函数，$x_i$是第i个训练样本，$\gamma$是动量因子，$G_t$是当前累积的梯度平方和，$\epsilon$是一个很小的数（通常取 $10^{-8}$），$\beta_1$和$\beta_2$分别是Adam算法中的两个指数加权平均因子。
