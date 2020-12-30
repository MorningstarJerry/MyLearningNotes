# K8s VS Docker Swarm

https://bbs.huaweicloud.com/blogs/140721

https://github.com/kubernetes/kubernetes/tags

https://juejin.cn/post/6844903943051411469

C:\Users\2294765\.kube

=========================

\>kubectl get pods -n kube-system

$TOKEN=((kubectl -n kube-system describe secret default | Select-String "token:") -split " +")[1]

kubectl config set-credentials docker-for-desktop --token="${TOKEN}“

echo $TOKEN

http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

<img src="C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201215104320322.png" alt="image-20201215104320322" style="zoom:80%;" />


eyJhbGciOiJSUzI1NiIsImtpZCI6IjJZbEprTVRTR1RJUjYtYzVaQ2lyUElNakNVbDlsUmpxS21TdDRXdEZPM1kifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJrdWJlLXN5c3RlbSIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VjcmV0Lm5hbWUiOiJkZWZhdWx0LXRva2VuLTY5ZmNoIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQubmFtZSI6ImRlZmF1bHQiLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC51aWQiOiIwMzVjMjIyOC0yZTY1LTQ0YzAtOWZjZS0zZmY5N2QwY2U0ODMiLCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6a3ViZS1zeXN0ZW06ZGVmYXVsdCJ9.SfBdIKGgUmNck5_3tkIBNW22QwX8nHtiU5blLR_0Z1p3aXDXCXkrCH_fO8rU4RcBlxEcNhRvvbb64YQ4FjTEOzBAYYOPpy95s6bEFB1D6-FsCyTMJjELRyB3q8zHuKaeTeCOCPmrWzrvjr405mEeIyqam7GX9FQYRXc1ucBzHOgxi_kH6Cu_anT-6EUPv6A9Mp-TjlH3o0JKL0Qtlb9brVwoBq2Jn0IiAQTf7_EUkSU37YT5KEH-r-bagOif1F5LwIP1y7KryYQ1KnX73I1nltAOvHTW3ESyEw4hE3HVqBev-W4eDCVechedVYfo8RUl9INBwW2qc5lJ_BKLd8BrXg



# 本地虚拟机构建 k8s 集群
https://github.com/rootsongjc/kubernetes-vagrant-centos-cluster