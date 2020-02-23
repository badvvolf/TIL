# requests stream으로 데이터 일부만 받기

reqeusts에 stream=True 옵션을 주면 직접 스트림을 컨트롤 할 수 있다. 데이터를 전부 받지 않고 처음에 끊어버리면 앞쪽 데이터만 받을 수도 있다. 

stream=true로 열었으면 끝나고 close 해주는 것을 잊지 말자.

```python
response = requests.get(url, stream=True)
print(response.status_code)

# stream 데이터 직접 읽기
# 더이상 데이터를 받기 싫다면 이를 생략하고 close하고 가면 됨
for chunk in response.iter_content(chunk_size=8192): 
	if chunk: # filter out keep-alive new chunks
		print(chunk)

response.close()
```


## 참고
* https://stackoverflow.com/questions/16694907/download-large-file-in-python-with-requests#16696317
* https://stackoverflow.com/questions/14270698/get-file-size-using-python-requests-while-only-getting-the-header