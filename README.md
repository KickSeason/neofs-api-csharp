# NeoFS API CSharp

### Requirements
- DotNet SDK
- protobuf / protoc

### Regenerate NeoFS Proto files and documentation
```
# DotNet Restore 
$ dotnet restore

# Regenerate proto files
$ make docgen protoc
```

### Example in Docker

`docker pull nspccdev/neofs-api-csharp:example`

```
→ docker run -it nspccdev/neofs-api-csharp:example
Examples for NeoFS API Library:

→ /app/cmd help
  put        put file into the container
  get        get file from the container
  help       Display more information on a specific command.
  version    Display version information.

→ /app/cmd get \
    --host s01.fs.nspcc.ru:8080 \
    --cid 35Zg4Mj8y998VDftVyQygFrQCPRTPvG8QK6WXhGUWPMH \
    --oid c9c26787-f26f-46fb-b703-3c97f64d158c \
    -o /tmp/1.mp4

Used host: s01.fs.nspcc.ru:8080

Message = NeoFS.API.State.HealthRequest => 9206009a0600
Hash = 042d9c823d05044b42784312fb8185653961835ac184388257014567b5aeef3c9592669a4a98d4d8095a741a5c660fb687c50d2d28bdf307e3d0e9b96fa7858f58
HealthResponse = { "Healthy": true, "Status": "OK" }

Message = NeoFS.API.Object.GetRequest => 0a340a10c9c26787f26f46fbb7033c97f64d158c12201ee2a41ac5eddf24d3757015d5114e6b9b74cc49b639421d98123198dedea5489206009a0600
Hash = 04b77d76f42ca28bc57449b7f5f30ee9fa2ad5aa1f00a5da30098fd1e5cc32213b32f2545cbac0e92447457a004928cbaaa651bdfdd7ee4b0a48d6b65e61bfa37c

Received object
PayloadLength = 30640240
Headers:
{ "UserHeader": { "Key": "plugin", "Value": "sendneofs" } }
{ "UserHeader": { "Key": "expired", "Value": "1585828048" } }
{ "UserHeader": { "Key": "filename", "Value": "cat_in_space.mp4" } }
{ "PublicKey": { "Value": "ArNiK/QBe9/jF8WK7V9MdT8ga324lgRvp9d0u8S/f43C" } }
{ "Verify": { "PublicKey": "A/mUroBdlbezF/FcJaPTVV/IkHKddoAu8T6d8clVx1kx", "KeySignature": "BKnKpl0e6+zDDHWObtpE3D269J4B2dzZQwl5D1el1ldLJUlp918xYsrLJDfTsHpGFGNdW1+Ro9NMXiw2QLsp02g=" } }
{ "HomoHash": "FMFKxLuYto/QHDKETtvIWz+AnaL8lIGWk2YMVjNX56lTXcAdALtAbpmEtCtEOJdqfLic9DrV053doXGeahMtMQ==" }
{ "PayloadChecksum": "uztXSsSVqlljHekJC4oRP8SFzMEbZMLSz67KyW+lRZ0=" }
{ "Integrity": { "HeadersChecksum": "URlh7q+9jnrxAIyuikDmEwWoBK8oGSNZ5jncwFU+uXA=", "ChecksumSignature": "BMu0zbpZtkqgjkUJ56DcffnHrIPmV5xaoyRs3LHmcF+Cdj98wi1u4q68Judjrdjx79GnOOkjb34wiC/Bo8rlD1A=" } }

Wait for chunks
........................
Close file
Shutdown connection.
```