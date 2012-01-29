# request.env
best place to passing rack vars to your application or controllers.
## All Rack keys
### "rack.url_scheme"
### "rack.errors"
### "rack.version"
### "rack.run_once"
### "rack.input"
### "rack.multithread"
### "rack.multiprocess"
### "rack.request.query_hash"
### "rack.methodoverride.original_method"
### "rack.session.options"
### "rack.request.query_string"
### "rack.session"
session hash

## All action_dispatch keys
### "action_dispatch.request.formats"
Array of Mime::Type instance.
[<Mime::Type:0x106e81618
    @string="application/json"
    @symbol=:json
    @synonyms=["text/x-json" "application/jsonrequest"]>]
### "action_dispatch.request.parameters"
params hash
### "action_dispatch.remote_ip"
<ActionDispatch::RemoteIp::RemoteIpGetter:0x10480d770
   @check_ip_spoofing=true
   @env={...},
   @trusted_proxies=
    /(^127\.0\.0\.1$|^(10|172\.(1[6-9]|2[0-9]|30|31)|192\.168)\.)/i>
### "action_dispatch.request.content_type"
### "action_dispatch.request.request_parameters"
### "action_dispatch.cookies"
### "action_dispatch.parameter_filter"
### "action_dispatch.show_exceptions"
### "action_dispatch.request.path_parameters"
### "action_dispatch.secret_token"
### "action_dispatch.request.query_parameters"
### "action_dispatch.request.unsigned_session_cookie"

## Basic http keys
### "HTTP_HOST"
### "HTTP_ACCEPT"
### "SERVER_NAME"
### "REQUEST_PATH"
### "HTTP_USER_AGENT"
### "REMOTE_HOST"
### "SERVER_PROTOCOL"
### "SERVER_SOFTWARE"
"WEBrick/1.3.1 (Ruby/1.8.7/2011-02-18)"
### "REMOTE_ADDR"
### "PATH_INFO"
### "SCRIPT_NAME"
### "HTTP_VERSION"
### "REQUEST_URI"
### "SERVER_PORT"
### "REQUEST_METHOD"
### "QUERY_STRING"
### "GATEWAY_INTERFACE"

## Other keys
### "warden"
Warden::Proxy instance.
### "action_controller.instance"
