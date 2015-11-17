# �ƶ��˻�������

����һƪ�ʼ�ժҪ����

## ����

- pixel
- Viewport
- Viewport Meta
- Viewport dome

## �ƶ�web����

- ��Ӧʽ����
- Flex ���Բ���

### Flexbox

�Զ������������

	display:-webkit-flex;
	flex:num;

ע����Ӧ�ð�ԭ��ȱ�Ϊ0��flex-

	justify-content:center;
	align-items:center;
	//������� ˮƽ��ֱ����


### Flex���Ժ�ģ��

����flex-direction

ȡֵ��row/column

���У�

	-webkit-flex-wrap:
	flex-wrap:
	flex-flow:

justify-content�������Ű�

align-self:��Ԫ�ظ��Ե��Ű�

align-items

- �ɰ� Flex-box
- �°� Flex

## ��Ӧʽ��ƣ�

- �ٷֱȲ���
- ����ͼƬ
- ���²��֣���ʾ������

�����ı����

	.intwoline {
		display:-webkit-box !inportant;
		overflow:hidden;

		text-overflow:ellipsis;
		word-break:break-all;

		-webkit-box-orient:vertical;
		-webkit-line-clamp:2;
	}

## ƪһ

### ����

��webǰ�˿��������������������㺬�壺

1. �豸���أ��豸��Ļ���������أ������κ��豸�����������ص������ǹ̶��ģ�
2. CSS���أ�����һ����������ظ������Ϊweb�����ߴ���ġ�

**�����Ԫ��������`width: 200px` ʱ�����Ԫ�صĿ�ȿ�Խ��200��CSS���ء�** ����������һ����Խ200���豸���أ����ڻ��Խ���ٸ��豸���أ���ȡ����**�ֻ���Ļ�����Ժ��û�������**��

1. webǰ���������ط�Ϊ**�豸����**��**CSS����**��
2. �����ű���Ϊ1:1��ʱ��һ��CSS���صĴ�С����һ���豸���صĴ�С��
3. һ��CSS���صĴ�С�ǿɱ�ģ������ú�����ҳ���ʱ��ʵ���Ͼ�������С��Ŵ�CSS���أ����豸�������۴�С�����������ǲ���ġ�

### �ӿ�

**�ӿ��� html �ĸ�Ԫ�أ��������ǳ��ӿ�Ϊ��ʼ�����顣**

html Ԫ�صİٷֱ��ǻ����ӿڵġ�

#### �����ӿ�

�����ӿڣ��ƶ���CSS���ֵ������ӿڣ���CSS���ֻ���ݲ����ӿ������㡣

Ҳ����˵�����ƶ��ˣ��ӿں���������ڽ����ڹ�����ʵ���ϣ������ӿ�Ҫ����������ڴ�Ķ�(���ֻ���ƽ��������������ӿڵĿ����768~1024����֮��)

��ѯ��

	document.documentElement.clientWidth
	document.documentElement.clientHeight
	document.body.clientWidth  //Ľ��

#### �Ӿ��ӿڣ��û����ڿ�����վ������

#### �����ӿڣ�������������Ҫ��ע���ӿ�

	<meta name="viewport" content="width=device-width" />

�������д�������ֻ������Ҫ�Ѳ����ӿ���Ϊ�����ӿ�

�ܽ᣺

1. ��PC�ˣ������ӿھ�����������ڣ�
2. ���ƶ��ˣ��ӿڱ���Ϊ�����������ӿڡ��Ӿ��ӿڣ�
3. �ƶ��˻���һ�������ӿڣ����ǲ����ӿڵ�����ߴ磬������Ĳ����ӿڡ���ע�������ӿڵĳߴ����豸��������Ĳ�ͬ����ͬ���������������˵����ν����
4. ���Խ������ӿڵĿ����Ϊ�����ӿڡ�

�ĵã�

1. ��ʼ�����ӿ���680~1024��ô��
2. �����ӿ����С����Ȼδ�ص����Ӿ��ӿڡ����� iphone5 ��320*568��
3. CSS�����ǻ��ڲ����ӿڵģ�
4. ͨ��meta�������ӿڵĿ����Ϊ�����ӿں�CSS���ֵ��ӿ�Ҳ��С�ˣ�
2. ��PC�ˣ������ӿھ�����������ڣ����Բ�������meta��
2. ���ֻ��ˣ�Ϊ�������������Ƶأ���ȣ���������meta��


### �豸���ر�(Device Pixel Ratio ��ƣ�DPR)

�豸���رȵļ��㹫ʽ����ʽ�����Ĵ�ǰ�᣺**���ű���Ϊ1**

�豸���ر�(DPR) = �豸���ظ��� / �����ӿ�CSS���ظ���(device-width)

�������ӿ�һ�����豸���رȶ��ڲ�ͬ���豸�ǲ�ͬ��

### ���ţ���С�Ŵ����CSS���ء�

CSS���صĴ�С�ǿɱ�ģ������ŴӼ���ʵ�ֵĽǶ����������ǷŴ����СCSS���صĹ��̡�

������˫ָ����ҳ���ʱ��ʵ�������ڷŴ����СCSS���ء�

### ý���ѯ

1. ���ý������ͣ����� screen, tv �ȣ�
2. ��Ⲽ���ӿڵ����ԣ������ӿڵĿ�߷ֱ��ʵȣ�
3. ������ز�ѯ��������������Ƿ�֧��ĳĳ���ԣ���һ�㲻���ۣ���Ϊ����Ŀǰ�����֧�ֵĹ��ܶ���web�������������ã�

e.g.

		@media all and (min-width: 321px) and (max-width: 400px){
			.box{
				background: red;
			}
		}

## ƪ��

psdԭ��ĳߴ��ǰ����豸������Ƶģ�������CSS�е���ʽ�ǻ��ڲ����ӿڵĳߴ����ġ�

��һƪ�Ĺ�ʽ��

>�豸���رȣ�DPR�� = �豸���ظ��� / �����ӿ����ظ�����device-width��

��Ƹ��ܿ�640px��iPhone5��,dpr=2�����������ӿ�device-width=320px.

�����������������Ƹ��ϲ��������Ŀ�߶��������š�

�����(�ֻ�)û�취��ʾ����һ�����ص�����ֵ�������(�ֻ�)���Զ����䲹ȫΪһ�����ؽ�����ʾ��

��������Ƹ��ϲ�������һ������ֵ������2�ͻ������⡣

���⣬ƪһ�ᵽ����ͬ�豸��DPR�ǲ�һ���ģ���1��2��3������2.5��������������г�����ҳ���޷��������豸�������ʾ��

### ˼·��

��������ܽ������ӿڵĳߴ�����Ϊ���豸���سߴ���ȵĻ����������Ǿͱ�֤�����ͼ��ҳ���1:1��ϵ����ô���ǾͿ���ֱ��ʹ�� psd �в����ĳߴ��ˣ�Ȼ���������ߴ���ֻ��У����ǽ��еȱ����ž�ok�ˡ�

meta ��ǩ�е�`width=device-width`��δ������յ��µĽ���ǣ��ò����ӿڵĳߴ���������ӿڵĳߴ硣

��ô��������ܸı������ӿڵĳߴ磬Ҳ�͸ı��˲����ӿڵĳߴ硣�����Ҫ�õ�ƪһ�ᵽ��**����**��

�Ͻ��ۣ�ʵ���ϣ�������Ҫ��С�ı��� = �豸���رȵĵ�����

��̬���� meta :

	<script>
	var scale = 1 / window.devicePixelRatio;
	document.querySelector('meta[name="viewport"]').setAttribute('content','width=device-width,initial-scale=' + scale + ', maximum-scale=' + scale + ', minimum-scale=' + scale + ', user-scalable=no');
	</script>

### rem

rem����Գߴ絥λ�������html��ǩ�����С�ĵ�λ
e.g. ��� html �� font-size = 18px; ��ô 1rem = 18px

### �ܽ�

1. �������ӿڴ�С��Ϊ�豸���سߴ磺

	var scale = 1 / window.devicePixelRatio;
	document.querySelector('meta[name="viewport"]').setAttribute('content','width=device-width,initial-scale=' + scale + ', maximum-scale=' + scale + ', minimum-scale=' + scale + ', user-scalable=no');

2. ��̬����html�����С��

	document.documentElement.style.fontSize = document.documentElement.clientWidth / 10 + 'px';

3. �����ͼ�еĳߴ绻���rem

Ԫ�ص�rem�ߴ� = Ԫ�ص�psd����������سߴ� / ��̬���õ�html��ǩ��font-sizeֵ

### ���װ������ܽ᣺

1. �õ����ͼ�������ҳ����ܿ�Ϊ�˺ü��㣬ȡ100px�� font-size��������ͼ�� iPhone6 ����ô������ľ���7.5rem�����ҳ���� iPhone5 ����ô������Ľ������6.4rem��

2. ��̬����html��ǩ��font-sizeֵ��

		document.documentElement.style.fontSize = document.documentElement.clientWidth / ��remΪ��λ��ҳ���ܿ� + 'px';

e.g.

iPhone6��
	
	document.documentElement.style.fontSize = document.documentElement.clientWidth / 7.5 + 'px';

iPhone5��
	
	document.documentElement.style.fontSize = document.documentElement.clientWidth / 6.4 + 'px';

3. ��ҳ��ʱ�������ͼ��px�ߴ����100�õ�rem�ߴ硣
4. ���Ա�������һ�������������С��Ҫʹ��rem���㡣


## ƪ��

����

### PPI��Pixel Per Inch��

��ʾ�豸����Ļ�������ܶ�

ͼƬ��أ���ӡʱ�ķֱ��ʻ��ӡ���Ĵ�ӡ����

��1Ӣ�絥λ�������ӵ�е�����Խ�࣬�ܶ�Խ��PPIֵ��Խ�ߡ�

�������ܶȵ�ʵ��������ʲô����������ʲô����߻�Ͷ��豸��ʾ��˵��ʲôӰ�죿

��LCD��ʾ�豸�У�ÿһ�����أ�pixel��Ҳ���Գ�֮Ϊdot������������������(subpixel)��������϶��ɡ�

��ʾ���ϵ����ؾ�����������(physical pixel)���豸����(device pixel)

�������������ҳ�棨ͨ����Ctrl�������������֣������ŵ���CSS���ء�

�ó�һ���ǳ���Ҫ�ĸ������CSS���ش�����ֻ��һ�����ֵ��

�ش���������⣺**PPI�е�pixelָ��Ӧ������������**

��[ά���ٿ�](http://en.wikipedia.org/wiki/Pixel_density)�в�ͬ�Ľ��͡�




























