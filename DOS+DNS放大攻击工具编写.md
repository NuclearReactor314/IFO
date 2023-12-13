![image](https://github.com/NuclearReactor314/IFO/assets/145520137/4e1ad569-9df2-4965-8664-926b62cbc939)

# 简易页面设置
添加5个文本框，用来接受用户输入的被攻击的ip，发送的端口，服务器ip，发送接口名称，查询的域名。

添加一个滑块用来控制攻击的强度。

添加两个按钮控制攻击的开始和停止。

# attack 按钮槽函数 “核心代码”

接受输入，并调用攻击函数

~~~
void Widget::on_attack_pushButton_clicked()
{
    QByteArray dstipstr = ui->dst_ip_Edit->text().toLatin1();
    QByteArray ifnamestr =  ui->ifname_Edit->text().toLatin1();
    QByteArray dnsipstr = ui->dns_Edit->text().toLatin1();
    QByteArray domainstr = ui->Domain_Edit->text().toLatin1();
dosattack=
new DosAttack(dstipstr,ifnamestr,ui->port_spinBox->value(),dnsipstr,ui->AttackLEVEL_Slider->value(),domainstr);
    dosattack->start();
}
~~~
