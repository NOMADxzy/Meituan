## 用到的Redis结构

### 一、String

```shell
Key: "login:code:{phohe}"
Value: {code}
TTL: 设置过期时间以实现自动登出
```

```shell
Key: "seckill:stock:{vounch_id}"
Value: {stock}
```

### 二、ZSET

```bash
# 点赞记录
Key: "blog:liked:{blog_id}"
Value: {user_id1:like_time1、user_id2:like_time2...}
```

```bash
# 收件箱
Key: "feed:{user_id}"
Value: {blog_id1:pub_time1、blog_id2:pub_time2...}
```

### 三、Map

```bash
# 商铺信息
Key: "login:token:{shop_id}"
Value: Shop{id,name,type,area,score,openHours}
TTL: 设置过期时间以实现自动登出
```

```bash
# 用户信息
Key: "cache:shop:{token}"
Value: UserDTO{id,nickname,icon}
TTL: 设置过期时间以实现自动登出
```

### 四、BITMAP

```bash
# 签到记录
Key: "sign:{yyyyMM}:{user_id}"
Value: bits{31}
```

### 五、SET

```shell
# 关注了哪些用户（求共同关注）
Key: "follows:{user_id}"
Value: {user_id1, user_id2, ...}
```

### 六、GEO

```shell
# 商铺地理位置
Key: "shop:geo:{type_id}"
Value: {(shop_id1, pos1),(shop_id2, pos2)}
```

### 七、Stream

```bash
# 订单消息队列
Key: "stream.orders"
Value: {(user_id, vouch_id, order_id)}
```

