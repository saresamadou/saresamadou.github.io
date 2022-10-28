Dockerize spring boot app
Dockerfile
https://github.com/wagoodman/dive

Multistage dockerfile

maven compiler plugin enable layers

java -Djarmode=layertools

cloud native buildpacks
https://springone.io/2020/sessions/spring-to-image

Liveness and readiness

- Liveness:
"Correcte if the internal state if the app is fine. External dependencies or the service itself might not respond correctly still
"Broken" if the internal state of the application is broken and restarting is the only way to fix

- Readiness:
."ACCEPTING_TRAFFIC" is a way to tell load balancers that the app is ready to serve requests
.The app is refusing if it considers that its load is too hight, or depending on its lifecycle stage(starting up, shutting down)

circuit breaker

AvailabilityChangeEvent.publish
