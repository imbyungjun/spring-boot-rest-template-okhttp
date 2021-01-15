# spring-boot-rest-template-okhttp

### Step 1. Add okhttp3 dependency
**build.gradle**
```gradle
dependencies {
    implementation 'org.springframework.boot:spring-boot-starter-web'
    implementation 'com.squareup.okhttp3:okhttp'
    ...
}
```

### Step 2. Add customized RestTemplate bean
```java
@Configuration
public class RestTemplateConfig {
    @Bean
    public RestTemplate restTemplate() {
        return new RestTemplateBuilder()
                .requestFactory(OkHttp3ClientHttpRequestFactory::new)
                .build();
    }
}
```
