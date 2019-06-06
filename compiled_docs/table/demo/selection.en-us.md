{"title":"Selectable","meta":{"title":"Selectable","description":"\n<p>Demo the selectable table.</p>\n","order":"1"},"codes":{"jsx":"import { Table, Icon, MenuButton } from '@alifd/next';\n\nconst { Item } = MenuButton;\n\nconst dataSource = () => {\n    const result = [];\n    for (let i = 0; i < 5; i++) {\n        result.push({\n            title: {name: `Quotation for 1PCS Nano ${3 + i}.0 controller compatible`},\n            id: 100306660940 + i,\n            time: 2000 + i\n        });\n    }\n    return result;\n};\nconst render = (value, index, record) => {\n    return <a href=\"javascript:;\">Remove({record.id})</a>;\n};\nconst onChange = (...args) => {\n    console.log(args);\n};\nconst selectItem = id => {\n    console.log(id);\n};\n\nReactDOM.render(<Table\n    dataSource={dataSource()}\n    rowSelection={{\n        onChange: onChange,\n        getProps: (record, index) => {\n            console.log(record, index);\n\n            return  index === 2 ? {\n                disabled: true,\n                children: index\n            } : {\n                children: index\n            };\n        },\n        columnProps: () => {\n            return {\n                lock: 'left',\n                width: 90,\n                align: 'center'\n            };\n        },\n        titleAddons: () => {\n            return <div>请选择</div>;\n        },\n        titleProps: () => {\n            return {\n                // remove the select all button\n                // style: {display: 'none'},\n                disabled: true,\n                children:\n                <MenuButton text onItemClick={selectItem} menuProps={{\n                    isSelectIconRight: true\n                }} >\n                    <Item key=\"odd\">odd</Item>\n                    <Item key=\"even\">even</Item>\n                </MenuButton>\n            };\n        }\n    }}>\n    <Table.Column title=\"Id\" dataIndex=\"id\" width={200}/>\n    <Table.Column title=\"Title\" dataIndex=\"title.name\" width={200}/>\n    <Table.Column title=\"Time\" dataIndex=\"time\" width={200}/>\n    <Table.Column cell={render} width={200}/>\n</Table>, mountNode);\n"},"body":"\n````jsx\nimport { Table, Icon, MenuButton } from '@alifd/next';\n\nconst { Item } = MenuButton;\n\nconst dataSource = () => {\n    const result = [];\n    for (let i = 0; i < 5; i++) {\n        result.push({\n            title: {name: `Quotation for 1PCS Nano ${3 + i}.0 controller compatible`},\n            id: 100306660940 + i,\n            time: 2000 + i\n        });\n    }\n    return result;\n};\nconst render = (value, index, record) => {\n    return <a href=\"javascript:;\">Remove({record.id})</a>;\n};\nconst onChange = (...args) => {\n    console.log(args);\n};\nconst selectItem = id => {\n    console.log(id);\n};\n\nReactDOM.render(<Table\n    dataSource={dataSource()}\n    rowSelection={{\n        onChange: onChange,\n        getProps: (record, index) => {\n            console.log(record, index);\n\n            return  index === 2 ? {\n                disabled: true,\n                children: index\n            } : {\n                children: index\n            };\n        },\n        columnProps: () => {\n            return {\n                lock: 'left',\n                width: 90,\n                align: 'center'\n            };\n        },\n        titleAddons: () => {\n            return <div>请选择</div>;\n        },\n        titleProps: () => {\n            return {\n                // remove the select all button\n                // style: {display: 'none'},\n                disabled: true,\n                children:\n                <MenuButton text onItemClick={selectItem} menuProps={{\n                    isSelectIconRight: true\n                }} >\n                    <Item key=\"odd\">odd</Item>\n                    <Item key=\"even\">even</Item>\n                </MenuButton>\n            };\n        }\n    }}>\n    <Table.Column title=\"Id\" dataIndex=\"id\" width={200}/>\n    <Table.Column title=\"Title\" dataIndex=\"title.name\" width={200}/>\n    <Table.Column title=\"Time\" dataIndex=\"time\" width={200}/>\n    <Table.Column cell={render} width={200}/>\n</Table>, mountNode);\n````","html":"<script>(function(){'use strict';\n\nvar _next = require('@alifd/next');\n\nvar Item = _next.MenuButton.Item;\n\n\nvar dataSource = function dataSource() {\n    var result = [];\n    for (var i = 0; i < 5; i++) {\n        result.push({\n            title: { name: 'Quotation for 1PCS Nano ' + (3 + i) + '.0 controller compatible' },\n            id: 100306660940 + i,\n            time: 2000 + i\n        });\n    }\n    return result;\n};\nvar render = function render(value, index, record) {\n    return React.createElement(\n        'a',\n        { href: 'javascript:;' },\n        'Remove(',\n        record.id,\n        ')'\n    );\n};\nvar onChange = function onChange() {\n    for (var _len = arguments.length, args = Array(_len), _key = 0; _key < _len; _key++) {\n        args[_key] = arguments[_key];\n    }\n\n    console.log(args);\n};\nvar selectItem = function selectItem(id) {\n    console.log(id);\n};\n\nReactDOM.render(React.createElement(\n    _next.Table,\n    {\n        dataSource: dataSource(),\n        rowSelection: {\n            onChange: onChange,\n            getProps: function getProps(record, index) {\n                console.log(record, index);\n\n                return index === 2 ? {\n                    disabled: true,\n                    children: index\n                } : {\n                    children: index\n                };\n            },\n            columnProps: function columnProps() {\n                return {\n                    lock: 'left',\n                    width: 90,\n                    align: 'center'\n                };\n            },\n            titleAddons: function titleAddons() {\n                return React.createElement(\n                    'div',\n                    null,\n                    '\\u8BF7\\u9009\\u62E9'\n                );\n            },\n            titleProps: function titleProps() {\n                return {\n                    // remove the select all button\n                    // style: {display: 'none'},\n                    disabled: true,\n                    children: React.createElement(\n                        _next.MenuButton,\n                        { text: true, onItemClick: selectItem, menuProps: {\n                                isSelectIconRight: true\n                            } },\n                        React.createElement(\n                            Item,\n                            { key: 'odd' },\n                            'odd'\n                        ),\n                        React.createElement(\n                            Item,\n                            { key: 'even' },\n                            'even'\n                        )\n                    )\n                };\n            }\n        } },\n    React.createElement(_next.Table.Column, { title: 'Id', dataIndex: 'id', width: 200 }),\n    React.createElement(_next.Table.Column, { title: 'Title', dataIndex: 'title.name', width: 200 }),\n    React.createElement(_next.Table.Column, { title: 'Time', dataIndex: 'time', width: 200 }),\n    React.createElement(_next.Table.Column, { cell: render, width: 200 })\n), mountNode);})()</script><div class=\"highlight\"><pre class=\"language-jsx\"><code class=\"language-jsx\"><span class=\"token keyword\">import</span> <span class=\"token punctuation\">{</span> Table<span class=\"token punctuation\">,</span> Icon<span class=\"token punctuation\">,</span> MenuButton <span class=\"token punctuation\">}</span> <span class=\"token keyword\">from</span> <span class=\"token string\">'@alifd/next'</span><span class=\"token punctuation\">;</span>\n\n<span class=\"token keyword\">const</span> <span class=\"token punctuation\">{</span> Item <span class=\"token punctuation\">}</span> <span class=\"token operator\">=</span> MenuButton<span class=\"token punctuation\">;</span>\n\n<span class=\"token keyword\">const</span> <span class=\"token function-variable function\">dataSource</span> <span class=\"token operator\">=</span> <span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n    <span class=\"token keyword\">const</span> result <span class=\"token operator\">=</span> <span class=\"token punctuation\">[</span><span class=\"token punctuation\">]</span><span class=\"token punctuation\">;</span>\n    <span class=\"token keyword\">for</span> <span class=\"token punctuation\">(</span><span class=\"token keyword\">let</span> i <span class=\"token operator\">=</span> <span class=\"token number\">0</span><span class=\"token punctuation\">;</span> i <span class=\"token operator\">&lt;</span> <span class=\"token number\">5</span><span class=\"token punctuation\">;</span> i<span class=\"token operator\">++</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n        result<span class=\"token punctuation\">.</span><span class=\"token function\">push</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">{</span>\n            title<span class=\"token punctuation\">:</span> <span class=\"token punctuation\">{</span>name<span class=\"token punctuation\">:</span> <span class=\"token template-string\"><span class=\"token string\">`Quotation for 1PCS Nano </span><span class=\"token interpolation\"><span class=\"token interpolation-punctuation punctuation\">${</span><span class=\"token number\">3</span> <span class=\"token operator\">+</span> i<span class=\"token interpolation-punctuation punctuation\">}</span></span><span class=\"token string\">.0 controller compatible`</span></span><span class=\"token punctuation\">}</span><span class=\"token punctuation\">,</span>\n            id<span class=\"token punctuation\">:</span> <span class=\"token number\">100306660940</span> <span class=\"token operator\">+</span> i<span class=\"token punctuation\">,</span>\n            time<span class=\"token punctuation\">:</span> <span class=\"token number\">2000</span> <span class=\"token operator\">+</span> i\n        <span class=\"token punctuation\">}</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n    <span class=\"token punctuation\">}</span>\n    <span class=\"token keyword\">return</span> result<span class=\"token punctuation\">;</span>\n<span class=\"token punctuation\">}</span><span class=\"token punctuation\">;</span>\n<span class=\"token keyword\">const</span> <span class=\"token function-variable function\">render</span> <span class=\"token operator\">=</span> <span class=\"token punctuation\">(</span><span class=\"token parameter\">value<span class=\"token punctuation\">,</span> index<span class=\"token punctuation\">,</span> record</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n    <span class=\"token keyword\">return</span> <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>a</span> <span class=\"token attr-name\">href</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>javascript:;<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">Remove(</span><span class=\"token punctuation\">{</span>record<span class=\"token punctuation\">.</span>id<span class=\"token punctuation\">}</span><span class=\"token plain-text\">)</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>a</span><span class=\"token punctuation\">></span></span><span class=\"token punctuation\">;</span>\n<span class=\"token punctuation\">}</span><span class=\"token punctuation\">;</span>\n<span class=\"token keyword\">const</span> <span class=\"token function-variable function\">onChange</span> <span class=\"token operator\">=</span> <span class=\"token punctuation\">(</span><span class=\"token parameter\"><span class=\"token operator\">...</span>args</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n    console<span class=\"token punctuation\">.</span><span class=\"token function\">log</span><span class=\"token punctuation\">(</span>args<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n<span class=\"token punctuation\">}</span><span class=\"token punctuation\">;</span>\n<span class=\"token keyword\">const</span> <span class=\"token function-variable function\">selectItem</span> <span class=\"token operator\">=</span> <span class=\"token parameter\">id</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n    console<span class=\"token punctuation\">.</span><span class=\"token function\">log</span><span class=\"token punctuation\">(</span>id<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n<span class=\"token punctuation\">}</span><span class=\"token punctuation\">;</span>\n\nReactDOM<span class=\"token punctuation\">.</span><span class=\"token function\">render</span><span class=\"token punctuation\">(</span><span class=\"token operator\">&lt;</span>Table\n    dataSource<span class=\"token operator\">=</span><span class=\"token punctuation\">{</span><span class=\"token function\">dataSource</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">}</span>\n    rowSelection<span class=\"token operator\">=</span><span class=\"token punctuation\">{</span><span class=\"token punctuation\">{</span>\n        onChange<span class=\"token punctuation\">:</span> onChange<span class=\"token punctuation\">,</span>\n        <span class=\"token function-variable function\">getProps</span><span class=\"token punctuation\">:</span> <span class=\"token punctuation\">(</span><span class=\"token parameter\">record<span class=\"token punctuation\">,</span> index</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n            console<span class=\"token punctuation\">.</span><span class=\"token function\">log</span><span class=\"token punctuation\">(</span>record<span class=\"token punctuation\">,</span> index<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n\n            <span class=\"token keyword\">return</span>  index <span class=\"token operator\">===</span> <span class=\"token number\">2</span> <span class=\"token operator\">?</span> <span class=\"token punctuation\">{</span>\n                disabled<span class=\"token punctuation\">:</span> <span class=\"token boolean\">true</span><span class=\"token punctuation\">,</span>\n                children<span class=\"token punctuation\">:</span> index\n            <span class=\"token punctuation\">}</span> <span class=\"token punctuation\">:</span> <span class=\"token punctuation\">{</span>\n                children<span class=\"token punctuation\">:</span> index\n            <span class=\"token punctuation\">}</span><span class=\"token punctuation\">;</span>\n        <span class=\"token punctuation\">}</span><span class=\"token punctuation\">,</span>\n        <span class=\"token function-variable function\">columnProps</span><span class=\"token punctuation\">:</span> <span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n            <span class=\"token keyword\">return</span> <span class=\"token punctuation\">{</span>\n                lock<span class=\"token punctuation\">:</span> <span class=\"token string\">'left'</span><span class=\"token punctuation\">,</span>\n                width<span class=\"token punctuation\">:</span> <span class=\"token number\">90</span><span class=\"token punctuation\">,</span>\n                align<span class=\"token punctuation\">:</span> <span class=\"token string\">'center'</span>\n            <span class=\"token punctuation\">}</span><span class=\"token punctuation\">;</span>\n        <span class=\"token punctuation\">}</span><span class=\"token punctuation\">,</span>\n        <span class=\"token function-variable function\">titleAddons</span><span class=\"token punctuation\">:</span> <span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n            <span class=\"token keyword\">return</span> <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>div</span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">请选择</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>div</span><span class=\"token punctuation\">></span></span><span class=\"token punctuation\">;</span>\n        <span class=\"token punctuation\">}</span><span class=\"token punctuation\">,</span>\n        <span class=\"token function-variable function\">titleProps</span><span class=\"token punctuation\">:</span> <span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n            <span class=\"token keyword\">return</span> <span class=\"token punctuation\">{</span>\n                <span class=\"token comment\">// remove the select all button</span>\n                <span class=\"token comment\">// style: {display: 'none'},</span>\n                disabled<span class=\"token punctuation\">:</span> <span class=\"token boolean\">true</span><span class=\"token punctuation\">,</span>\n                children<span class=\"token punctuation\">:</span>\n                <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">MenuButton</span></span> <span class=\"token attr-name\">text</span> <span class=\"token attr-name\">onItemClick</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span>selectItem<span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">menuProps</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token punctuation\">{</span>\n                    isSelectIconRight<span class=\"token punctuation\">:</span> <span class=\"token boolean\">true</span>\n                <span class=\"token punctuation\">}</span><span class=\"token punctuation\">}</span></span> <span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n                    </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Item</span></span> <span class=\"token attr-name\">key</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>odd<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">odd</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Item</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n                    </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Item</span></span> <span class=\"token attr-name\">key</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>even<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">even</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Item</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n                </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">MenuButton</span></span><span class=\"token punctuation\">></span></span>\n            <span class=\"token punctuation\">}</span><span class=\"token punctuation\">;</span>\n        <span class=\"token punctuation\">}</span>\n    <span class=\"token punctuation\">}</span><span class=\"token punctuation\">}</span><span class=\"token operator\">></span>\n    <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Table.Column</span></span> <span class=\"token attr-name\">title</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>Id<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">dataIndex</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>id<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">width</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token number\">200</span><span class=\"token punctuation\">}</span></span><span class=\"token punctuation\">/></span></span>\n    <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Table.Column</span></span> <span class=\"token attr-name\">title</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>Title<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">dataIndex</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>title.name<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">width</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token number\">200</span><span class=\"token punctuation\">}</span></span><span class=\"token punctuation\">/></span></span>\n    <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Table.Column</span></span> <span class=\"token attr-name\">title</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>Time<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">dataIndex</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>time<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">width</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token number\">200</span><span class=\"token punctuation\">}</span></span><span class=\"token punctuation\">/></span></span>\n    <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Table.Column</span></span> <span class=\"token attr-name\">cell</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span>render<span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">width</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token number\">200</span><span class=\"token punctuation\">}</span></span><span class=\"token punctuation\">/></span></span>\n<span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Table</span></span><span class=\"token punctuation\">></span></span><span class=\"token punctuation\">,</span> mountNode<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span></code></pre></div>"}