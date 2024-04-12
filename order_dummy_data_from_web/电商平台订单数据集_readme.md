---
License:
    - CC0 公共领域共享

Ext:
    - .csv

DatasetUsage:
    - 126186995
---

## **背景描述**
本数据集是由巴西市场上最大的百货公司Olist慷慨提供的。Olist将巴西各地的小企业与渠道连接起来，没有麻烦，只需签订一份合同。这些商家能够通过Olist商店销售他们的产品，并通过Olist的物流合作伙伴将产品直接运送给客户。在我们的网站上看到更多信息：www.olist.com

客户从Olist Store购买产品后，卖家会接到通知来完成该订单。一旦客户收到产品，或预计交货日期到期，客户会通过电子邮件收到一份满意度调查，他可以对购买体验进行说明并写下一些评论。

> 注意：
> 一个订单可能有多个项目。
每件商品可能由不同的卖家来完成。
所有识别商店和合作伙伴的文字都用《权力的游戏》中的大家族名称进行了替换。


&nbsp;
## **数据说明**

**【数据架构】**
为了更好地理解和组织，这些数据被划分为多个数据集。在使用时，请参考以下数据架构。

![Image Name](https://cdn.kesci.com/upload/image/rq6agb2ubs.png?imageView2/0/w/960/h/960)


- **`olist_customers_dataset.csv`**

| 字段                         | 说明                               |
|----------------------------|----------------------------------|
| customer_id                | 键到订单数据集。每个订单都有一个唯一的customer_id。  |
| customer_unique_id  | 客户的唯一标识符。                        |
| customer_zip_code_prefix   | 客户邮编的前五位数字                       |
| customer_city              | 客户的城市名称                          |
| customer_state             | 客户所在州                            |

- **`olist_geolocation_dataset.csv`**

| 字段                           | 说明        |
|------------------------------|-----------|
| geolocation_zip_code_prefix  | 邮政编码的前5位  |
| geolocation_lat              | 纬度        |
| geolocation_lng              | 经度        |
| geolocation_city             | 城市名称      |
| geolocation_state            | 州         |

- **`olist_order_items_dataset.csv`**

| 字段                                 | 说明                                 |
|------------------------------------|------------------------------------|
| order_id                           | 订单唯一标识符                            |
| order_item_id               | 识别同一订单中包含的商品数量的顺序号。                |
| product_id                  | 产品唯一标识符                            |
| seller_id                   | 卖方唯一标识符                            |
| shipping_limit_date  | 显示卖方处理订单移交给物流伙伴的运输限制日期。            |
| price                              | 物品价格                               |
| freight_value                      | 货品运费项目（如果一个订单有一个以上的商品，运费将被分割成以下几部分 |

- **`olist_order_payments_dataset.csv`**

| 字段                       | 说明                                            |
|--------------------------|-----------------------------------------------|
| order_id                 | 一个订单的唯一标识符。                                   |
| payment_sequential       | 一个客户可以用一种以上的支付方式支付订单。如果他这样做，将创建一个序列来容纳所有的付款。  |
| text_formatpayment_type  | 客户选择的付款方式。                                    |
| payment_installments     | 客户选择的分期付款的数量。                                 |
| payment_value            | 交易价值。                                         |

- **`olist_order_reviews_dataset.csv`**

| 字段                                     | 说明                      |
|----------------------------------------|-------------------------|
| review_id                              | 唯一的审查标识符                |
| order_id                        | 唯一的订单标识符                |
| review_score                           | 顾客在满意度调查中给出的从1到5不等的注释。  |
| review_comment_title                   | 顾客留下的评论标题，以葡萄牙语写成。      |
| review_comment_message                 | 来自顾客评论的评论信息，以葡萄牙语显示。    |
| calendar_todayreview_creation_date     | 显示发送给顾客的满意度调查的日期。       |
| calendar_todayreview_answer_timestamp  | 显示满意度调查答案的时间戳。          |


-  **`olist_orders_dataset.csv`**

| 字段                                           | 说明                                 |
|----------------------------------------------|------------------------------------|
| order_id                                     | 订单的唯一标识符。                          |
| customer_id                           | 是客户数据集的关键。每个订单都有一个唯一的customer_id。  |
| order_status                                 | 对订单状态的参考（已交付、已发货等）。                |
| calendar_todayorder_purchase_timestamp       | 显示购买时间戳。                           |
| calendar_todayorder_approved_at              | 显示付款批准的时间戳。                        |
| calendar_todayorder_delivered_carrier_date   | 显示订单发布的时间戳。当它被处理给物流合作伙伴。           |
| calendar_todayorder_delivered_customer_date  | 显示实际订单交付给客户的日期。                    |
| calendar_todayorder_estimated_delivery_date  | 显示在购买时通知客户的预计交货日期。                 |

- **`olist_products_dataset.csv`**

| 字段                               | 说明               |
|----------------------------------|------------------|
| product_id                       | 唯一的产品标识符         |
| text_formatproduct_category_name | 产品的根类别，以葡萄牙语表示。  |
| product_name_lenght              | 从产品名称中提取的字符数。    |
| product_description_lenght       | 从产品描述中提取的字符数。    |
| product_photos_qty               | 公布的产品照片的数量       |
| product_weight_g                 | 产品重量，以克计。        |
| product_length_cm                | 产品长度，以厘米为单位。     |
| product_height_cm                | 产品高度，以厘米为单位。     |
| product_width_cm                 | 产品宽度以厘米为单位。      |

- **`olist_sellers_dataset.csv`**

| 字段                      | 说明          |
|-------------------------|-------------|
| seller_id               | 卖方唯一标识符     |
| seller_zip_code_prefix  | 卖方邮政编码的前5位  |
| seller_city             | 卖方城市名称      |
| seller_state            | 卖方州         |

- **`product_category_name_translation.csv`**

| 字段                             | 说明          |
|--------------------------------|-------------|
| product_category_name          | 葡萄牙语中的类别名称  |
| product_category_name_english  | 英文的类别名称     |


&nbsp;
## **问题描述**
RFM分析
销售额预测
客户满意度分析

## **引用格式**
```
@misc{data5034,
    title = { 电商平台订单数据集 },
    author = { 鲸神小火 },
    howpublished = { \url{https://www.heywhale.com/mw/dataset/63ee1f10470e19e0b56d12ee} },
    year = { 2023 },
}
```