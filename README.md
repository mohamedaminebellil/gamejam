# gamejam
<h1>clear
clc
rsb=0:2:20
for k=1:length(rsb)
    x=randn(1,100)
    for i=1:100
        
        if x(i)<0
           x(i)=0;
        else
           x(i)=1;
        end
    end
    for j=1:100
        if x(j)==0
            xm(j)=-1;
        else 
            xm(j)=1;
        end
    end
    
    
    sigma=(1/sqrt(2))*10^(-rsb(k)/40)
    bruit=sigma*randn(1,100)
    for l=1:100
        y(l)=bruit(l)+xm(l);
    end
    figure(1)
    plot(real(xm),imag(xm),"*")
    figure(2)
    plot(real(y),imag(y),"o")
    for f=1:length(y)
        if y(f)<0
            y(f)=0;
        else
            y(f)=1;
        end
    end
    nb=0
    for h=1:length(x)
        if x(h)~=xm(h)
            nb=nb+1;
        end
    end
    teb(k)=nb/length(x);
end
figure(3)
plot(rsb,teb)</h1>
