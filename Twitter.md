#  트위터 타임 라인에 글쓰기
``` python
import tweepy
import datetime

consumer_key = "본인의 consumer_key"
consumer_secret = "본인의 consumer_secret"

#트위터 애플리케이션의 인가를 수행
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
access_token = "본인의 access_token"
access_token_secret = "본인의 access_token_secret"

#객체에 액세스 토큰 지정
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth)

#트위터 포스트 
tweet = '타임라인에 쓰고 싶은 글'
api.update_status(status=tweet)
print('Successfully Posted')
print()

#타임 라인 읽어오기(본인이 지금 올린 것 까지 확인 가능
public_tweets = api.home_timeline() 
for tweet in public_tweets:
print(tweet.text)
```
