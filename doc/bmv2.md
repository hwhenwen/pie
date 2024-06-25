# bmv2 数据结构分析

1. ParserLookAhead 偏移报文指针前的读取操作
    1. make 访问偏移报文
    1. peek 复制解析报文

1. ParserOpSet 对报文的解析操作集
    1. ParserOpSet<field_t>::operator() 重载提取报文域段
    1. ParserOpSet<Data>::operator()
    重载提取报文数据内容
    1.ParserOpSet<ParserLookAhead>::operator()
    重载提取报文域段内容并解析
    1. ParserOpSet<ArithExpression>::operator()重载函数通过表达式设置域段内容

    
