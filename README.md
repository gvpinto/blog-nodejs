#Stashing

```
     -
        name: Build and push comments image
        uses: docker/build-push-action@v4
        with:
          context: ./comments
          file: ./comments/Dockerfile
          push: true
          tags: ${{ secrets.DOCKERHUB_USERNAME }}/comments:latest
      -
        name: Build and push query image
        uses: docker/build-push-action@v4
        with:
          context: ./query
          file: ./query/Dockerfile
          push: true
          tags: ${{ secrets.DOCKERHUB_USERNAME }}/query:latest
      -
        name: Build and push moderation image
        uses: docker/build-push-action@v4
        with:
          context: ./moderation
          file: ./moderation/Dockerfile
          push: true
          tags: ${{ secrets.DOCKERHUB_USERNAME }}/moderation:latest
      -
        name: Build and push event-bus image
        uses: docker/build-push-action@v4
        with:
          context: ./event-bus
          file: ./event-bus/Dockerfile
          push: true
          tags: ${{ secrets.DOCKERHUB_USERNAME }}/event-bus:latest

```