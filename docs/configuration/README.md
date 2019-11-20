## Configuration

You can configure the following settings in the application with environment variables:

### Transcoding related configuration:

The project uses [Lumberjack](https://github.com/natefinch/lumberjack) for the log rotation of the ffmpeg transcoding processes.

#### RTSP_STREAM_CLEANUP_TIME
Default: `2m0s`<br/>
Type: string<br/>
Description: Time period for the cleanup process [info on format here](https://golang.org/pkg/time/#ParseDuration)<br/>

#### RTSP_STREAM_STORE_DIR
Default: `./videos`<br/>
Type: string<br/>
Description: Sub directory to store the video chunks<br/>

#### RTSP_STREAM_KEEP_FILES
Default: `false`<br/>
Type: bool<br/>
Description: Option to keep the chunks for the stream being transcoded<br/>

#### RTSP_STREAM_PROCESS_LOGGING_ENABLED
Default: `false`<br/>
Type: bool<br/>
Description: Indicates if logging of transcoding ffmpeg processes is enabled or not<br/>

#### RTSP_STREAM_PROCESS_LOGGING_DIR
Default: `/var/log/rtsp-stream`<br/>
Type: string<br/>
Description: Describes the directory where ffmpeg process logs are stored<br/>

#### RTSP_STREAM_PROCESS_LOGGING_MAX_SIZE
Default: `500`<br/>
Type: integer<br/>
Description: Maximum size of each log file in **megabytes** for retention<br/>

#### RTSP_STREAM_PROCESS_LOGGING_MAX_AGE
Default: `7`<br/>
Type: integer<br/>
Description: Maximum number of days that we store a given log file<br/>

#### RTSP_STREAM_PROCESS_LOGGING_MAX_BACKUPS
Default: `3`<br/>
Type: integer<br/>
Description: Maximum number of old log files to retain for each ffmpeg process<br/>

#### RTSP_STREAM_PROCESS_LOGGING_COMPRESS
Default: `true`<br/>
Type: bool<br/>
Description: Option to compress the rotated log file or not<br/>

<hr/>

### HTTP related configuration:

#### RTSP_STREAM_PORT
Default: `8080`<br/>
Type: integer<br/>
Description: Port where the application listens<br/>

#### RTSP_STREAM_DEBUG
Default: `false`<br/>
Type: bool<br/>
Description: Turns on / off debug features<br/>

#### RTSP_STREAM_LIST_ENDPOINT
Default: `false`<br/>
Type: bool<br/>
Description: Turns on / off the `/list` endpoint<br/>

<hr/>

### CORS related configuration

By default all origin is allowed to make requests to the server, but you might want to configure it for security reasons.

#### RTSP_STREAM_CORS_ENABLED
Default: `false`<br/>
Type: bool<br/>
Description: Indicates if cors should be handled as configured or as default (everything allowed)<br/>

#### RTSP_STREAM_CORS_ALLOWED_ORIGIN
Default: <br/>
Type: []string<br/>
Description: A list of origins a cross-domain request can be executed from<br/>

#### RTSP_STREAM_CORS_ALLOW_CREDENTIALS
Default: `false`<br/>
Type: bool<br/>
Description: Indicates whether the request can include user credentials like cookies, HTTP authentication or client side SSL certificates<br/>

#### RTSP_STREAM_CORS_MAX_AGE
Default: `0`<br/>
Type: integer<br/>
Description: Indicates how long (in seconds) the results of a preflight request can be cached<br/>