import streamlit as st  

st.title("欢迎来到登陆界面")  
ac=st.text_input("用户名")  
pa=st.text_input("密码")  
if st.button("登录"):  
    print(ac,pa)  
    with open ("accont.txt","r") as f:  
            acc=[line.split(" ") for line in f.readlines()]  
            print(acc)  
            st.write(acc)  
            for bb in acc:  
             st.write(acc)  
             if ac == bb[0]:  
                with open("password.txt", "r") as b:  
                    abc = [line.split(" ") for line in b.readlines()]  
                    for aa in abc:  
                     if pa == aa[0]:  
                        st.write("登录成功")  
                     else:  
                        st.write("密码错误")  
            else:  
                st.write("用户名错误")  
st.divider()  
if 'bp' not in st.session_state:  
        st.session_state.bp=0  
if st.button("注册"):  
        st.session_state.bp=not st.session_state.bp  
if st.session_state.bp:  
     zhucezhanghao = st.text_input("请输入您想注册的账号")  
     zhucemima = st.text_area("请输入您想注册的密码")  
     if st.button("确定"):  
      with open("accont.txt", "a") as f:  
        f.write(f"{zhucezhanghao}\n")  
      with open("password.txt", "a") as f:  
         f.write(f"{zhucemima}\n")  
      st.session_state.bp =0
