FROM node:18 as build

WORKDIR /app
COPY code/ .
ARG REACT_APP_API_URL
ENV REACT_APP_API_URL="${REACT_APP_API_URL:-http://localhost:5000/todos}"
RUN npm install
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]