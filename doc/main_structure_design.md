# pie仿真主要数据结构设计

## 1. local metadata
    1. 该结构用来描述在标准metadata之外，报文解析可能需要的其他metadata
    ``` demo
    struct local_metadata{
        uint32_t cur_state;
        uint32_t key[4];
        uint32_t cur_state;
        uint32_t l2_offset;
        uint32_t l3_offset;
        uint32_t l4_offset;
        uint32_t is_udp_tcp;
        uint32_t has_vlan;
        uint32_t is_ipv4_ipv6;
        uint32_t option1;
        uint32_t option2;
    }
    ```

## psi
    1. 该结构用来描述一个packet 仿真实例，该结构用来存储报文解析过程中的header结构, 以及对报文的操作函数
    ``` demo
    class psi{
        public:
            // ...... 此处有报文的操作函数
        private:
            std::vector<Header> headers;
    }
    ```

## header结构
    1. 该结构用来描述报文的头部定义
    ``` demo
    class header{
        public:
            int get_header_length();
            int pre_append_header(int nbytes);
            int append_header(int nbytes);
            
        private:
            std::vector<char> header_section_buffer;
    }
    ```
