StreamDevil SDK for JavaScript
==============================

StreamDevil provides an intelligent peer-assisted streaming infrastructure on top of your existing CDN. It radically reduces your CDN bandwidth and allows you to serve the highest video quality at lower cost. 
You can find a demo [here](https://streamdevil.io/vod-demo/).

## Basic Integration Sample

```html
<!doctype html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>StreamDevil Basic Integration</title>

        <!-- StreamDevil SDK include -->
        <script type="text/javascript" src="./streamdevil-sdk.js"></script>
    </head>
    <body>
        <video id="player" width="600" height="300" class="video-js vjs-default-skin" controls muted></video>
        
        <script type="application/javascript">
            var player = document.getElementById('player');
    
            // StreamDevil SDK initialization
            var streamDevil = new StreamDevilSDK({
                debug: true // only for development
            });
        
            // StreamDevil wrap video source
            streamDevil.setSrc({
                target: player,
                src: '/static/demo/big-buck-bunny.mp4', 
                srcUid: 'big-buck-bunny.mp4.sdm'
            }, function (error) {
                if (error) {
                    // fallback to plain source 
                    player.src = '/static/demo/big-buck-bunny.mp4';
                    console.log(error);
                    return;
                }
                player.play();
            });
        </script>
    </body>
</html>
```

## Integration Documentations

You can find documentation [here](https://streamdevil.github.com/streamdevil-sdk-js).

## StreamDevil Dashboard

Coming soon.