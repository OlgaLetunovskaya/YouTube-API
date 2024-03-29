# Тестирование методов для работы с видео YouTube
## Данный README-файл содержит информацию о тестировании методов для работы с видео в YouTube с использованием Postman.

### Начало работы
Для использования методов нужно выполнить следующие шаги:

#### 1. Получение API ключа:  
Создать профиль разработчика в Google.  
Войти в Google-консоль и создать новый проект.  
Включить для проекта доступ к YouTube API в разделе "API и сервисы".  
В разделе "Учетные данные" создать новый API ключ, который будет использоваться для отправки запросов.  
#### 2. Получение access_token:  
Создать OAuth клиент в разделе "Учетные данные" в Google Developers Console.  
Указать https://www.getpostman.com/oauth2/callback в качестве коллбек URL.  
Получить client ID и client secret.  
#### 3. Настройка Postman:  
Создать новую коллекцию и запросы для каждого из тестируемых методов.   
В настройках коллекции в разделе "Authorization" выбрать тип "API Key" и указать полученный API ключ.  
В каждом запросе добавить API ключ в заголовки запроса с помощью ключа Authorization и значения <API_KEY>.  
#### Тестирование методов  
Позитивные  
Получение списка видео по id   
GET https://www.googleapis.com/youtube/v3/videos?part=snippet&id=jifUJrYPZQQ&<API_KEY>  
Постановка лайка на видео  
POST https://www.googleapis.com/youtube/v3/videos/rate?rating=like&id=jifUJrYPZQQ&<API_KEY>&<access_token>  
Получение списка самых популярных видео  
GET https://www.googleapis.com/youtube/v3/videos?part=snippet&chart=mostPopular&<API_KEY>  
Негативные  
Получение списка видео по некорректному id   
GET https://www.googleapis.com/youtube/v3/videos?part=snippet&id=jifUJrYPZQQ&<API_KEY>  
Постановка повторного лайка на видео  
POST https://www.googleapis.com/youtube/v3/videos/rate?rating=like&id=jifUJrYPZQQ&<API_KEY>&<access_token>  
Получение списка самых популярных видео без API_key    
GET https://www.googleapis.com/youtube/v3/videos?part=snippet&chart=mostPopular&<API_KEY> 
#### Запуск коллекции  
Открыть Postman.  
Импортировать созданную коллекцию.  
В коллекции выбрать каждый запрос и нажать "Send" для отправки запроса.  
Проверить ответы на соответствие ожидаемым результатам.  
