import base64


def encodeJpeg(imgpath):
    f=open(imgpath,'rb')
    data=f.read()
    f.close()
    base64data=base64.b64encode(data)
    return base64data.decode()

def decodeJpeg(imgpath,data):
    jpgdata=base64.b64decode(data)
    f=open(imgpath,'wb')
    f.write(jpgdata)
    f.close()
x=(encodeJpeg("123"))
decodeJpeg(r"444.jpg",x)
