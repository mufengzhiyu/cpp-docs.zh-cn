---
title: "CMenu 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMenu
- AFXWIN/CMenu
- AFXWIN/CMenu::CMenu
- AFXWIN/CMenu::AppendMenu
- AFXWIN/CMenu::Attach
- AFXWIN/CMenu::CheckMenuItem
- AFXWIN/CMenu::CheckMenuRadioItem
- AFXWIN/CMenu::CreateMenu
- AFXWIN/CMenu::CreatePopupMenu
- AFXWIN/CMenu::DeleteMenu
- AFXWIN/CMenu::DeleteTempMap
- AFXWIN/CMenu::DestroyMenu
- AFXWIN/CMenu::Detach
- AFXWIN/CMenu::DrawItem
- AFXWIN/CMenu::EnableMenuItem
- AFXWIN/CMenu::FromHandle
- AFXWIN/CMenu::GetDefaultItem
- AFXWIN/CMenu::GetMenuContextHelpId
- AFXWIN/CMenu::GetMenuInfo
- AFXWIN/CMenu::GetMenuItemCount
- AFXWIN/CMenu::GetMenuItemID
- AFXWIN/CMenu::GetMenuItemInfo
- AFXWIN/CMenu::GetMenuState
- AFXWIN/CMenu::GetMenuString
- AFXWIN/CMenu::GetSafeHmenu
- AFXWIN/CMenu::GetSubMenu
- AFXWIN/CMenu::InsertMenu
- AFXWIN/CMenu::InsertMenuItem
- AFXWIN/CMenu::LoadMenu
- AFXWIN/CMenu::LoadMenuIndirect
- AFXWIN/CMenu::MeasureItem
- AFXWIN/CMenu::ModifyMenu
- AFXWIN/CMenu::RemoveMenu
- AFXWIN/CMenu::SetDefaultItem
- AFXWIN/CMenu::SetMenuContextHelpId
- AFXWIN/CMenu::SetMenuInfo
- AFXWIN/CMenu::SetMenuItemBitmaps
- AFXWIN/CMenu::SetMenuItemInfo
- AFXWIN/CMenu::TrackPopupMenu
- AFXWIN/CMenu::TrackPopupMenuEx
- AFXWIN/CMenu::m_hMenu
dev_langs: C++
helpviewer_keywords:
- CMenu [MFC], CMenu
- CMenu [MFC], AppendMenu
- CMenu [MFC], Attach
- CMenu [MFC], CheckMenuItem
- CMenu [MFC], CheckMenuRadioItem
- CMenu [MFC], CreateMenu
- CMenu [MFC], CreatePopupMenu
- CMenu [MFC], DeleteMenu
- CMenu [MFC], DeleteTempMap
- CMenu [MFC], DestroyMenu
- CMenu [MFC], Detach
- CMenu [MFC], DrawItem
- CMenu [MFC], EnableMenuItem
- CMenu [MFC], FromHandle
- CMenu [MFC], GetDefaultItem
- CMenu [MFC], GetMenuContextHelpId
- CMenu [MFC], GetMenuInfo
- CMenu [MFC], GetMenuItemCount
- CMenu [MFC], GetMenuItemID
- CMenu [MFC], GetMenuItemInfo
- CMenu [MFC], GetMenuState
- CMenu [MFC], GetMenuString
- CMenu [MFC], GetSafeHmenu
- CMenu [MFC], GetSubMenu
- CMenu [MFC], InsertMenu
- CMenu [MFC], InsertMenuItem
- CMenu [MFC], LoadMenu
- CMenu [MFC], LoadMenuIndirect
- CMenu [MFC], MeasureItem
- CMenu [MFC], ModifyMenu
- CMenu [MFC], RemoveMenu
- CMenu [MFC], SetDefaultItem
- CMenu [MFC], SetMenuContextHelpId
- CMenu [MFC], SetMenuInfo
- CMenu [MFC], SetMenuItemBitmaps
- CMenu [MFC], SetMenuItemInfo
- CMenu [MFC], TrackPopupMenu
- CMenu [MFC], TrackPopupMenuEx
- CMenu [MFC], m_hMenu
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 104c965da403040308386e019d56684577318eee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="cmenu-class"></a>CMenu 类
封装 Windows `HMENU`。  
  
## <a name="syntax"></a>语法  
  
```  
class CMenu : public CObject  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CMenu::CMenu](#cmenu)|构造 `CMenu` 对象。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[CMenu::AppendMenu](#appendmenu)|将新的项追加到此菜单的末尾。|  
|[CMenu::Attach](#attach)|将附加的 Windows 菜单句柄`CMenu`对象。|  
|[CMenu::CheckMenuItem](#checkmenuitem)|旁边放置一个复选标记，或从弹出菜单的菜单项中删除复选标记。|  
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|将菜单项旁边的单选按钮，并从所有组中的其他菜单项中移除的单选按钮。|  
|[CMenu::CreateMenu](#createmenu)|创建一个空的菜单，并将其附加到`CMenu`对象。|  
|[CMenu::CreatePopupMenu](#createpopupmenu)|创建一个空的弹出菜单，并将其附加到`CMenu`对象。|  
|[CMenu::DeleteMenu](#deletemenu)|从菜单中删除指定的项。 如果菜单项具有关联的弹出菜单，销毁弹出菜单的句柄并释放由它的内存。|  
|[CMenu::DeleteTempMap](#deletetempmap)|删除任何临时`CMenu`创建的对象`FromHandle`成员函数。|  
|[CMenu::DestroyMenu](#destroymenu)|销毁附加到的菜单`CMenu`对象并释放任何菜单占用的内存。|  
|[CMenu::Detach](#detach)|分离从 Windows 菜单句柄`CMenu`对象并返回的句柄。|  
|[CMenu::DrawItem](#drawitem)|由框架在所有者绘制菜单更改的可视方面时调用。|  
|[CMenu::EnableMenuItem](#enablemenuitem)|启用、 禁用，或将使变灰 （灰色） 菜单项。|  
|[CMenu::FromHandle](#fromhandle)|返回一个指向`CMenu`提供了 Windows 菜单句柄的对象。|  
|[CMenu::GetDefaultItem](#getdefaultitem)|确定指定的菜单上的默认菜单项。|  
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|检索与菜单相关联的帮助上下文 ID。|  
|[CMenu::GetMenuInfo](#getmenuinfo)|检索特定菜单上的信息。|  
|[CMenu::GetMenuItemCount](#getmenuitemcount)|确定弹出窗口或顶级菜单中的项的数目。|  
|[CMenu::GetMenuItemID](#getmenuitemid)|获取位于指定位置的菜单项的菜单项标识符。|  
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|检索有关菜单项的信息。|  
|[CMenu::GetMenuState](#getmenustate)|在弹出菜单中返回指定的菜单项或项的数目的状态。|  
|[CMenu::GetMenuString](#getmenustring)|检索指定的菜单项的标签。|  
|[CMenu::GetSafeHmenu](#getsafehmenu)|返回`m_hMenu`包装此`CMenu`对象。|  
|[CMenu::GetSubMenu](#getsubmenu)|检索指向弹出菜单的指针。|  
|[CMenu::InsertMenu](#insertmenu)|在移动该菜单下的其他项的指定位置插入新菜单项。|  
|[CMenu::InsertMenuItem](#insertmenuitem)|在菜单中指定位置插入新菜单项。|  
|[CMenu::LoadMenu](#loadmenu)|从可执行文件中加载的菜单资源，并将其附加到`CMenu`对象。|  
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|从内存中的菜单模板加载一个菜单，并将其附加到`CMenu`对象。|  
|[CMenu::MeasureItem](#measureitem)|由框架调用以确定菜单维度，创建一个所有者绘制菜单时。|  
|[CMenu::ModifyMenu](#modifymenu)|更改现有菜单项中指定的位置。|  
|[CMenu::RemoveMenu](#removemenu)|从指定的菜单中删除具有关联的弹出菜单的菜单项。|  
|[CMenu::SetDefaultItem](#setdefaultitem)|将指定菜单默认菜单项设置。|  
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|设置要与菜单相关联的帮助上下文 ID。|  
|[CMenu::SetMenuInfo](#setmenuinfo)|在特定的菜单上设置的信息。|  
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|将指定的选中标记位图与菜单项相关联。|  
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|更改菜单项有关的信息。|  
|[CMenu::TrackPopupMenu](#trackpopupmenu)|在指定位置显示浮动的弹出菜单，并在弹出菜单上跟踪选定的项。|  
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|在指定位置显示浮动的弹出菜单，并在弹出菜单上跟踪选定的项。|  
  
### <a name="public-operators"></a>公共运算符  
  
|名称|描述|  
|----------|-----------------|  
|[CMenu::operator HMENU](#operator_hmenu)|检索菜单对象的句的柄。|  
|[CMenu::operator ！ =](#operator_neq)|确定两个菜单对象是否不相等。|  
|[CMenu::operator = =](#operator_eq_eq)|确定两个菜单对象是否相等。|  
  
### <a name="public-data-members"></a>公共数据成员  
  
|名称|描述|  
|----------|-----------------|  
|[CMenu::m_hMenu](#m_hmenu)|指定附加到的 Windows 菜单的句柄`CMenu`对象。|  
  
## <a name="remarks"></a>备注  
 它提供用于创建、 跟踪、 更新和销毁菜单的成员函数。  
  
 创建`CMenu`对象上以本地的堆栈帧，然后调用`CMenu`的成员函数以操作新菜单上，根据需要。 接下来，调用[CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu)若要将菜单设置为一个窗口，后面紧跟调用`CMenu`对象的[分离](#detach)成员函数。 `CWnd::SetMenu`成员函数设置到新菜单的窗口的菜单、 导致窗口重绘以反映菜单更改，并还会将菜单的所有权传递到窗口。 调用**分离**分离`HMENU`从`CMenu`对象，这样，当本地`CMenu`变量超出范围，`CMenu`对象析构函数不会尝试销毁菜单它没有再拥有。 销毁窗口时，将自动销毁本身的菜单。  
  
 你可以使用[LoadMenuIndirect](#loadmenuindirect)成员函数来创建中的菜单的模板在内存中，但通过资源通过调用创建一个菜单[LoadMenu](#loadmenu)更易于维护和菜单资源本身可以创建和修改通过菜单编辑器。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenu`  
  
## <a name="requirements"></a>惠?  
 **标头:** afxwin.h  
  
##  <a name="appendmenu"></a>CMenu::AppendMenu  
 将新的项追加到末尾的菜单。  
  
```  
BOOL AppendMenu(
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL AppendMenu(
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>参数  
 `nFlags`  
 添加到菜单时，请指定有关新的菜单项的状态信息。 它包含一个或多个备注部分中列出的值。  
  
 `nIDNewItem`  
 指定新的菜单项的命令 ID 或者，如果`nFlags`设置为**MF_POPUP**，菜单句柄 ( `HMENU`) 的弹出菜单。 `nIDNewItem`忽略参数 （不需要） 如果`nFlags`设置为**MF_SEPARATOR**。  
  
 `lpszNewItem`  
 指定新的菜单项的内容。 `nFlags`参数用于解释`lpszNewItem`方式如下：  
  
|nFlags|LpszNewItem 的解释|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|包含应用程序提供 32 位值，应用程序可以用来维护与菜单项关联的附加数据。 在处理时，此 32 位的值是应用程序`WM_MEASUREITEM`和`WM_DRAWITEM`消息。 值存储在**itemData**提供与这些消息的结构的成员。|  
|**MF_STRING**|包含指向以 null 结尾的字符串的指针。 这是默认解释。|  
|**MF_SEPARATOR**|`lpszNewItem` （不需要），则忽略参数。|  
  
 *pBmp*  
 指向`CBitmap`将用作菜单项的对象。  
  
### <a name="return-value"></a>返回值  
 如果该函数成功，则为非 0；否则为 0。  
  
### <a name="remarks"></a>备注  
 应用程序可以通过设置中的值指定菜单项的状态`nFlags`。 当`nIDNewItem`指定弹出菜单中，它将成为追加到的菜单的一部分。 如果该菜单将被销毁，附加的菜单还将被销毁。 应从分离附加的菜单`CMenu`对象以避免冲突。 请注意， **MF_STRING**和`MF_OWNERDRAW`不是有效的位图版本`AppendMenu`。  
  
 以下列表描述可能在中设置的标志`nFlags`:  
  
- **MF_CHECKED**充当与一个切换开关**MF_UNCHECKED**放置项旁边的默认复选标记。 当应用程序提供选中标记位图 (请参阅[SetMenuItemBitmaps](#setmenuitembitmaps)成员函数)，显示"复选标记"位图。  
  
- **MF_UNCHECKED**充当与一个切换开关**MF_CHECKED**删除项旁边的复选标记。 当应用程序提供选中标记位图 (请参阅`SetMenuItemBitmaps`成员函数)，显示"复选标记关闭"位图。  
  
- **MF_DISABLED**禁用菜单项，以便它不能选择，但不是 dim 它。  
  
- `MF_ENABLED`启用菜单项，以便它可以选择并将其还原从其灰显状态。  
  
- **MF_GRAYED**禁用菜单项，以便它不能同时选择和它的模糊。  
  
- **MF_MENUBARBREAK**将置于新行在静态菜单或弹出菜单中的新列中的项。 用垂直的分隔线，将与旧列分隔新的弹出菜单列。  
  
- **MF_MENUBREAK**将置于新行在静态菜单或弹出菜单中的新列中的项。 无分隔线位于各列之间。  
  
- `MF_OWNERDRAW`指定项目的所有者描述项。 当首次显示菜单时，拥有菜单窗口接收`WM_MEASUREITEM`消息，检索的高度和宽度的菜单项。 `WM_DRAWITEM`消息是发送每当所有者必须更新菜单项的可视外观。 此选项不是有效的顶级菜单项。  
  
- **MF_POPUP**指定菜单项具有与之相关联的弹出菜单。 ID 参数指定是要与项相关联的弹出菜单的句柄。 这用于将顶级的弹出菜单或分层的弹出菜单添加到弹出菜单项。  
  
- **MF_SEPARATOR**绘制水平的分隔线。 仅可在弹出菜单。 无法灰显，禁用，或突出显示此行。 其他参数将被忽略。  
  
- **MF_STRING**指定菜单项是字符字符串。  
  
 每个以下的组列出标志是互斥的不能一起使用：  
  
- **MF_DISABLED**， `MF_ENABLED`，和**MF_GRAYED**  
  
- **MF_STRING**， `MF_OWNERDRAW`， **MF_SEPARATOR**，和位图版本  
  
- **MF_MENUBARBREAK**和**MF_MENUBREAK**  
  
- **MF_CHECKED**和**MF_UNCHECKED**  
  
 每当驻留在的菜单 （无论窗口会显示），一个窗口发生更改时，应用程序应调用[CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::CreateMenu](#createmenu)。  
  
##  <a name="attach"></a>CMenu::Attach  
 将附加到现有 Windows 菜单`CMenu`对象。  
  
```  
BOOL Attach(HMENU hMenu);
```  
  
### <a name="parameters"></a>参数  
 `hMenu`  
 指定一个 Windows 菜单的句柄。  
  
### <a name="return-value"></a>返回值  
 如果该操作成功，则非零否则为 0。  
  
### <a name="remarks"></a>备注  
 如果已附加到一个菜单，不应该调用此函数`CMenu`对象。 菜单句柄存储在`m_hMenu`数据成员。  
  
 如果你想要操作的菜单已与窗口关联，则可以使用[CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu)函数可获取菜单的句柄。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="checkmenuitem"></a>CMenu::CheckMenuItem  
 添加到的复选标记，或从弹出菜单中的菜单项中删除复选标记。  
  
```  
UINT CheckMenuItem(
    UINT nIDCheckItem,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>参数  
 `nIDCheckItem`  
 指定要检查的菜单项，所确定的那样`nCheck`。  
  
 `nCheck`  
 指定如何检查菜单项以及如何确定在菜单中的项的位置。 `nCheck`参数可以是的组合**MF_CHECKED**或**MF_UNCHECKED**与**MF_BYPOSITION**或**MF_BYCOMMAND**标志。 可以使用按位 OR 运算符组合这些标志。 它们具有以下含义：  
  
- **MF_BYCOMMAND**指定参数提供的命令 ID 的现有的菜单项。 这是默认设置。  
  
- **MF_BYPOSITION**指定参数提供现有的菜单项的位置。 第一项位于位置 0。  
  
- **MF_CHECKED**充当与一个切换开关**MF_UNCHECKED**放置项旁边的默认复选标记。  
  
- **MF_UNCHECKED**充当与一个切换开关**MF_CHECKED**删除项旁边的复选标记。  
  
### <a name="return-value"></a>返回值  
 项的前一状态： **MF_CHECKED**或**MF_UNCHECKED**，或如果菜单项不存在的 0xFFFFFFFF。  
  
### <a name="remarks"></a>备注  
 `nIDCheckItem`参数指定要修改的项。  
  
 `nIDCheckItem`参数可识别的弹出菜单项，以及菜单项。 检查弹出菜单项不需任何特殊步骤。 无法检查顶级菜单项。 必须按位置检查的弹出菜单项，因为它不具有与之关联的菜单项标识符。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::GetMenuState](#getmenustate)。  
  
##  <a name="checkmenuradioitem"></a>CMenu::CheckMenuRadioItem  
 检查指定的菜单项，并使其单选项。  
  
```  
BOOL CheckMenuRadioItem(
    UINT nIDFirst,  
    UINT nIDLast,  
    UINT nIDItem,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>参数  
 `nIDFirst`  
 指定 (ID 或偏移量，具体取决于的值作为`nFlags`) 中的单选按钮组的第一个菜单项。  
  
 `nIDLast`  
 指定 (ID 或偏移量，具体取决于的值作为`nFlags`) 中的单选按钮组的最后一个菜单项。  
  
 `nIDItem`  
 指定 (ID 或偏移量，具体取决于的值作为`nFlags`) 将检查与单选按钮组中的项。  
  
 `nFlags`  
 指定解释`nIDFirst`， `nIDLast`，和`nIDItem`方式如下：  
  
|nFlags|解释|  
|------------|--------------------|  
|**MF_BYCOMMAND**|指定参数提供的命令 ID 的现有的菜单项。 这是默认值，如果既没有**MF_BYCOMMAND**也不**MF_BYPOSITION**设置。|  
|**MF_BYPOSITION**|指定参数提供现有的菜单项的位置。 第一项位于位置 0。|  
  
### <a name="return-value"></a>返回值  
 如果成功，则非零否则为 0  
  
### <a name="remarks"></a>备注  
 同时，该函数取消选中关联组中的所有其他菜单项，并清除这些项的单选项类型标志。 将显示已选中的项，而不选中标记位图使用单选按钮 （或项目符号） 位图。  
  
### <a name="example"></a>示例  
  请参阅示例[ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range)。  
  
##  <a name="cmenu"></a>CMenu::CMenu  
 创建一个空的菜单，并将其附加到`CMenu`对象。  
  
```  
CMenu();
```  
  
### <a name="remarks"></a>备注  
 直到你调用的创建或加载成员函数之一，才会创建菜单**CMenu:**  
  
- [CreateMenu](#createmenu)  
  
- [CreatePopupMenu](#createpopupmenu)  
  
- [LoadMenu](#loadmenu)  
  
- [LoadMenuIndirect](#loadmenuindirect)  
  
- [附加](#attach)  
  
##  <a name="createmenu"></a>CMenu::CreateMenu  
 创建一个菜单，并将其附加到`CMenu`对象。  
  
```  
BOOL CreateMenu();
```  
  
### <a name="return-value"></a>返回值  
 如果成功，则创建菜单则不为否则为 0。  
  
### <a name="remarks"></a>备注  
 菜单是最初为空。 可通过使用添加菜单项`AppendMenu`或`InsertMenu`成员函数。  
  
 如果菜单分配给一个窗口，它将自动销毁销毁窗口时。  
  
 在退出之前, 应用程序必须释放系统资源与菜单关联，如果菜单未分配给一个窗口。 应用程序通过调用释放菜单[DestroyMenu](#destroymenu)成员函数。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]  
  
##  <a name="createpopupmenu"></a>CMenu::CreatePopupMenu  
 创建弹出菜单，并将其附加到`CMenu`对象。  
  
```  
BOOL CreatePopupMenu();
```  
  
### <a name="return-value"></a>返回值  
 如果已成功创建弹出菜单; 则为非 0否则为 0。  
  
### <a name="remarks"></a>备注  
 菜单是最初为空。 可通过使用添加菜单项`AppendMenu`或`InsertMenu`成员函数。 应用程序可以添加到现有菜单或弹出菜单的弹出菜单。 `TrackPopupMenu`可能使用成员函数，来显示此菜单为浮动的弹出菜单以及跟踪的弹出菜单上选择。  
  
 如果菜单分配给一个窗口，它将自动销毁销毁窗口时。 如果菜单添加到现有菜单中，它将自动销毁该菜单时销毁。  
  
 在退出之前, 应用程序必须释放系统资源与弹出菜单关联，如果菜单未分配给一个窗口。 应用程序通过调用释放菜单[DestroyMenu](#destroymenu)成员函数。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::CreateMenu](#createmenu)。  
  
##  <a name="deletemenu"></a>CMenu::DeleteMenu  
 从菜单中删除的项。  
  
```  
BOOL DeleteMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>参数  
 `nPosition`  
 指定是要删除所确定的那样的菜单项`nFlags`。  
  
 `nFlags`  
 用于解释`nPosition`方式如下：  
  
|nFlags|NPosition 的解释|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|指定参数提供的命令 ID 的现有的菜单项。 这是默认值，如果既没有**MF_BYCOMMAND**也不**MF_BYPOSITION**设置。|  
|**MF_BYPOSITION**|指定参数提供现有的菜单项的位置。 第一项位于位置 0。|  
  
### <a name="return-value"></a>返回值  
 如果该函数成功，则为非 0；否则为 0。  
  
### <a name="remarks"></a>备注  
 如果菜单项具有关联的弹出菜单中，`DeleteMenu`销毁弹出菜单的句柄并释放使用弹出菜单的内存。  
  
 每当驻留在的菜单 （无论窗口会显示），一个窗口发生更改时，应用程序必须调用[CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)。  
  
### <a name="example"></a>示例  
  请参阅示例[CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu)。  
  
##  <a name="deletetempmap"></a>CMenu::DeleteTempMap  
 自动调用`CWinApp`空闲时间处理程序中，删除任何临时`CMenu`创建的对象[FromHandle](#fromhandle)成员函数。  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>备注  
 `DeleteTempMap`分离附加到一个临时的 Windows 菜单对象`CMenu`对象在删除之前`CMenu`对象。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]  
  
##  <a name="destroymenu"></a>CMenu::DestroyMenu  
 销毁菜单和任何使用的 Windows 资源。  
  
```  
BOOL DestroyMenu();
```  
  
### <a name="return-value"></a>返回值  
 当菜单被破坏; 则为非 0否则为 0。  
  
### <a name="remarks"></a>备注  
 从分离菜单`CMenu`对象被销毁之前。 Windows`DestroyMenu`自动调用函数`CMenu`析构函数。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::CreateMenu](#createmenu)。  
  
##  <a name="detach"></a>CMenu::Detach  
 分离从一个 Windows 菜单`CMenu`对象并返回的句柄。  
  
```  
HMENU Detach();
```  
  
### <a name="return-value"></a>返回值  
 句柄，类型`HMENU`，到 Windows 菜单中，如果成功，否则为**NULL**。  
  
### <a name="remarks"></a>备注  
 `m_hMenu`数据成员设置为**NULL**。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="drawitem"></a>CMenu::DrawItem  
 由框架在所有者绘制菜单更改的可视方面时调用。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>参数  
 `lpDrawItemStruct`  
 指向的指针[DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)结构，其中包含有关所需的绘图的类型的信息。  
  
### <a name="remarks"></a>备注  
 `itemAction`的成员`DRAWITEMSTRUCT`结构定义要执行的绘制操作。 重写该成员函数以实现所有者描述的绘图`CMenu`对象。 应用程序应还原选择的显示上下文中提供的所有图形设备接口 (GDI) 对象`lpDrawItemStruct`之前的此成员函数终止。  
  
 请参阅[CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)有关的说明`DRAWITEMSTRUCT`结构。  
  
### <a name="example"></a>示例  
 下面的代码是从 MFC [CTRLTEST](../../visual-cpp-samples.md)示例：  
  
 [!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]  
  
##  <a name="enablemenuitem"></a>CMenu::EnableMenuItem  
 启用、 禁用，或调低亮度菜单项。  
  
```  
UINT EnableMenuItem(
    UINT nIDEnableItem,  
    UINT nEnable);
```  
  
### <a name="parameters"></a>参数  
 *nIDEnableItem*  
 指定要启用的菜单项所确定的那样`nEnable`。 弹出菜单项，以及标准菜单项，可以指定此参数。  
  
 `nEnable`  
 指定要执行的操作。 它可以是的组合**MF_DISABLED**， `MF_ENABLED`，或**MF_GRAYED**，与**MF_BYCOMMAND**或**MF_BYPOSITION**。 可以使用按位 OR 运算符组合这些值。 这些值的含义如下：  
  
- **MF_BYCOMMAND**指定参数提供的命令 ID 的现有的菜单项。 这是默认设置。  
  
- **MF_BYPOSITION**指定参数提供现有的菜单项的位置。 第一项位于位置 0。  
  
- **MF_DISABLED**禁用菜单项，以便它不能选择，但不是 dim 它。  
  
- `MF_ENABLED`启用菜单项，以便它可以选择并将其还原从其灰显状态。  
  
- **MF_GRAYED**禁用菜单项，以便它不能同时选择和它的模糊。  
  
### <a name="return-value"></a>返回值  
 以前的状态 ( **MF_DISABLED**， `MF_ENABLED`，或**MF_GRAYED**) 或为-1 是否有效。  
  
### <a name="remarks"></a>备注  
 [CreateMenu](#createmenu)， [InsertMenu](#insertmenu)， [ModifyMenu](#modifymenu)，和[LoadMenuIndirect](#loadmenuindirect)成员函数还可以设置的状态 （已启用，禁用，或变暗） 的菜单项。  
  
 使用**MF_BYPOSITION**值需要应用程序使用正确`CMenu`。 如果`CMenu`的菜单栏时，受影响的顶级菜单项 （在菜单栏中的项）。 若要设置弹出窗口或嵌套的弹出菜单，按位置中的项的状态，应用程序必须指定`CMenu`的弹出菜单。  
  
 当应用程序指定了**MF_BYCOMMAND**标志，Windows 将检查隶属于的所有弹出菜单项`CMenu`; 因此，除非存在重复的菜单项时，使用`CMenu`的菜单栏是足够。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]  
  
##  <a name="fromhandle"></a>CMenu::FromHandle  
 返回一个指向`CMenu`赋予一个菜单的 Windows 句柄的对象。  
  
```  
static CMenu* PASCAL FromHandle(HMENU hMenu);
```  
  
### <a name="parameters"></a>参数  
 `hMenu`  
 菜单 Windows 句柄。  
  
### <a name="return-value"></a>返回值  
 指向的指针`CMenu`这可能是临时的还是永久。  
  
### <a name="remarks"></a>备注  
 如果`CMenu`对象尚未附加到 Windows 菜单对象，一个临时`CMenu`创建对象并将其附加。  
  
 此临时`CMenu`对象只有在应用程序在其事件循环，删除这段时间的所有临时对象具有空闲时间的下一步时才有效。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::CreateMenu](#createmenu)。  
  
##  <a name="getdefaultitem"></a>CMenu::GetDefaultItem  
 确定指定的菜单上的默认菜单项。  
  
```  
UINT GetDefaultItem(
    UINT gmdiFlags,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>参数  
 *gmdiFlags*  
 值，该值指定该函数搜索菜单项的方式。 此参数可以为 none、 一个，或以下值的组合：  
  
|“值”|含义|  
|-----------|-------------|  
|**GMDI_GOINTOPOPUPS**|指定，是否默认项目是指打开一个子菜单，该函数是相应的子菜单以递归方式在其中进行搜索。 如果子菜单中没有默认项，则返回的值标识用于打开子菜单项。<br /><br /> 默认情况下，该函数返回在指定菜单上，不管它是用于打开子菜单项的第一个默认项。|  
|**GMDI_USEDISABLED**|指定，该函数是返回一个默认项，即使它处于禁用状态。<br /><br /> 默认情况下，该函数将跳过已禁用或显示为灰色的项。|  
  
 `fByPos`  
 值，该值指定是否检索菜单项的标识符或其位置。 如果此参数为**FALSE**，返回标识符。 否则，返回的位置。  
  
### <a name="return-value"></a>返回值  
 如果函数成功，则返回值是标识符或菜单项的位置。 如果函数失败，返回值为-1。  
  
### <a name="remarks"></a>备注  
 此成员函数实现的 Win32 函数的行为[GetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647976)，如 Windows SDK 中所述。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::InsertMenu](#insertmenu)。  
  
##  <a name="getmenucontexthelpid"></a>CMenu::GetMenuContextHelpId  
 检索与 ID 关联的上下文帮助`CMenu`。  
  
```  
DWORD GetMenuContextHelpId() const;  
```  
  
### <a name="return-value"></a>返回值  
 与当前关联 ID 的上下文帮助`CMenu`如果它有一个; 否则为零。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::InsertMenu](#insertmenu)。  
  
##  <a name="getmenuinfo"></a>CMenu::GetMenuInfo  
 检索一个菜单的信息。  
  
```  
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;  
```  
  
### <a name="parameters"></a>参数  
 `lpcmi`  
 指向的指针[MENUINFO](http://msdn.microsoft.com/library/windows/desktop/ms647575)结构，它包含菜单上的信息。  
  
### <a name="return-value"></a>返回值  
 如果函数成功，返回值为非零值;否则，返回值为零。  
  
### <a name="remarks"></a>备注  
 调用此函数可检索有关菜单上的信息。  
  
##  <a name="getmenuitemcount"></a>CMenu::GetMenuItemCount  
 确定弹出窗口或顶级菜单中的项的数目。  
  
```  
UINT GetMenuItemCount() const;  
```  
  
### <a name="return-value"></a>返回值  
 如果该函数成功，则菜单中的项的数目否则为-1。  
  
### <a name="example"></a>示例  
  请参阅示例[CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu)。  
  
##  <a name="getmenuitemid"></a>CMenu::GetMenuItemID  
 获取位于位置定义的菜单项的菜单项标识符`nPos`。  
  
```  
UINT GetMenuItemID(int nPos) const;  
```  
  
### <a name="parameters"></a>参数  
 `nPos`  
 指定的位置 （从零开始） 的菜单项正在检索其 ID。  
  
### <a name="return-value"></a>返回值  
 如果该函数成功的弹出菜单中指定的项的项 ID。 如果指定的项是一个弹出菜单 （而不是弹出菜单中的项），则返回值为-1。 如果`nPos`对应于**分隔符**菜单项，返回值为 0。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::InsertMenu](#insertmenu)。  
  
##  <a name="getmenuiteminfo"></a>CMenu::GetMenuItemInfo  
 检索有关菜单项的信息。  
  
```  
BOOL GetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>参数  
 `uItem`  
 标识符或要获取其相关信息的菜单项的位置。 此参数的含义取决于值`ByPos`。  
  
 `lpMenuItemInfo`  
 指向的指针[MENUITEMINFO](http://msdn.microsoft.com/library/windows/desktop/ms647578)，如下所述在 Windows SDK 中，包含有关菜单上的信息。  
  
 `fByPos`  
 值，该值指定的含义`nIDItem`。 默认情况下，`ByPos`是**FALSE**，指示该 uItem 是菜单项标识符。 如果`ByPos`未设置为**FALSE**，它指示菜单项位置。  
  
### <a name="return-value"></a>返回值  
 如果函数成功，则返回值不为零。 如果函数失败，则返回值为零。 若要获得扩展的错误信息，请使用 Win32 函数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)，如 Windows SDK 中所述。  
  
### <a name="remarks"></a>备注  
 此成员函数实现的行为的 Win32 函数[GetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms647980)，如 Windows SDK 中所述。 请注意，在的 MFC 实现`GetMenuItemInfo`，不要使用菜单的句柄。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]  
  
##  <a name="getmenustate"></a>CMenu::GetMenuState  
 在弹出菜单中返回指定的菜单项或项的数目的状态。  
  
```  
UINT GetMenuState(
    UINT nID,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>参数  
 `nID`  
 指定的菜单项 ID，由`nFlags`。  
  
 `nFlags`  
 指定的性质`nID`。 它可以是以下值之一：  
  
- **MF_BYCOMMAND**指定参数提供的命令 ID 的现有的菜单项。 这是默认设置。  
  
- **MF_BYPOSITION**指定参数提供现有的菜单项的位置。 第一项位于位置 0。  
  
### <a name="return-value"></a>返回值  
 值为 0xFFFFFFFF，如果指定的项不存在。 如果*nId*标识弹出菜单中，高序位字节包含弹出菜单中的项的数目，低序位字节包含弹出菜单与关联的菜单标志。 否则返回值都属于以下列表中的值的掩码 （布尔值或） (此掩码准确地描述菜单的状态项*nId*标识):  
  
- **MF_CHECKED**充当与一个切换开关**MF_UNCHECKED**放置项旁边的默认复选标记。 当应用程序提供选中标记位图 (请参阅`SetMenuItemBitmaps`成员函数)，显示"复选标记"位图。  
  
- **MF_DISABLED**禁用菜单项，以便它不能选择，但不是 dim 它。  
  
- `MF_ENABLED`启用菜单项，以便它可以选择并将其还原从其灰显状态。 请注意此常量的值为 0;使用此值时，应用程序不应测试针对失败的 0。  
  
- **MF_GRAYED**禁用菜单项，以便它不能同时选择和它的模糊。  
  
- **MF_MENUBARBREAK**将置于新行在静态菜单或弹出菜单中的新列中的项。 用垂直的分隔线，将与旧列分隔新的弹出菜单列。  
  
- **MF_MENUBREAK**将置于新行在静态菜单或弹出菜单中的新列中的项。 无分隔线位于各列之间。  
  
- **MF_SEPARATOR**绘制水平的分隔线。 仅可在弹出菜单。 无法灰显，禁用，或突出显示此行。 其他参数将被忽略。  
  
- **MF_UNCHECKED**充当与一个切换开关**MF_CHECKED**删除项旁边的复选标记。 当应用程序提供选中标记位图 (请参阅`SetMenuItemBitmaps`成员函数)，显示"复选标记关闭"位图。 请注意此常量的值为 0;使用此值时，应用程序不应测试针对失败的 0。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]  
  
##  <a name="getmenustring"></a>CMenu::GetMenuString  
 将指定的菜单项的标签复制到指定的缓冲区。  
  
```  
int GetMenuString(
    UINT nIDItem,  
    LPTSTR lpString,  
    int nMaxCount,  
    UINT nFlags) const;  
  
int GetMenuString(
    UINT nIDItem,  
    CString& rString,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>参数  
 `nIDItem`  
 在菜单中，根据的值中指定的整数标识符的菜单项或菜单项的偏移量`nFlags`。  
  
 `lpString`  
 指向以将接收标签的缓冲区。  
  
 `rString`  
 对引用`CString`是接收复制的菜单字符串的对象。  
  
 `nMaxCount`  
 指定要复制的标签的最大长度 （以字符为单位）。 如果标签的长度超过中指定的最大`nMaxCount`，额外的字符将被截断。  
  
 `nFlags`  
 指定的解释`nIDItem`参数。 它可以是以下值之一：  
  
|nFlags|NIDItem 的解释|  
|------------|-------------------------------|  
|**MF_BYCOMMAND**|指定参数提供的命令 ID 的现有的菜单项。 这是默认值，如果既没有**MF_BYCOMMAND**也不**MF_BYPOSITION**设置。|  
|**MF_BYPOSITION**|指定参数提供现有的菜单项的位置。 第一项位于位置 0。|  
  
### <a name="return-value"></a>返回值  
 指定的实际将复制到缓冲区，不包括 null 终止符的字符数。  
  
### <a name="remarks"></a>备注  
 `nMaxCount`参数应为一个大于中的标签，以适应终止字符串的 null 字符的字符数。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::InsertMenu](#insertmenu)。  
  
##  <a name="getsafehmenu"></a>CMenu::GetSafeHmenu  
 返回`HMENU`包装此`CMenu`对象，或**NULL** `CMenu`指针。  
  
```  
HMENU GetSafeHmenu() const;  
```  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::LoadMenu](#loadmenu)。  
  
##  <a name="getsubmenu"></a>CMenu::GetSubMenu  
 检索`CMenu`的弹出菜单的对象。  
  
```  
CMenu* GetSubMenu(int nPos) const;  
```  
  
### <a name="parameters"></a>参数  
 `nPos`  
 指定菜单中包含的弹出菜单的位置。 位置值从 0 开始，第一个菜单项。 无法在此函数中使用弹出菜单的标识符。  
  
### <a name="return-value"></a>返回值  
 指向的指针`CMenu`对象，其`m_hMenu`成员包含弹出菜单的句柄，如果一个弹出菜单位于给定位置; 否则为**NULL**。 如果`CMenu`对象不存在，则将创建一个临时。 `CMenu`应不会存储返回的指针。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::TrackPopupMenu](#trackpopupmenu)。  
  
##  <a name="insertmenu"></a>CMenu::InsertMenu  
 在指定位置插入新菜单项`nPosition`菜单中向下移动其他项。  
  
```  
BOOL InsertMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL InsertMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>参数  
 `nPosition`  
 指定要在其前面新菜单项是要插入的菜单项。 `nFlags`参数可以用于解释`nPosition`通过以下方式：  
  
|nFlags|NPosition 的解释|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|指定参数提供的命令 ID 的现有的菜单项。 这是默认值，如果既没有**MF_BYCOMMAND**也不**MF_BYPOSITION**设置。|  
|**MF_BYPOSITION**|指定参数提供现有的菜单项的位置。 第一项位于位置 0。 如果`nPosition`为-1，新的菜单项追加到菜单的末尾。|  
  
 `nFlags`  
 指定如何`nPosition`被解释且添加到菜单时指定有关新的菜单项的状态信息。 有关可能设置的标志的列表，请参阅[AppendMenu](#appendmenu)成员函数。 若要指定多个值，使用按位 OR 运算符合并它们与**MF_BYCOMMAND**或**MF_BYPOSITION**标志。  
  
 `nIDNewItem`  
 指定新的菜单项的命令 ID 或者，如果`nFlags`设置为**MF_POPUP**，菜单句柄 ( `HMENU`) 的弹出菜单。 `nIDNewItem`忽略参数 （不需要） 如果`nFlags`设置为**MF_SEPARATOR**。  
  
 `lpszNewItem`  
 指定新的菜单项的内容。 `nFlags`可以用于解释`lpszNewItem`通过以下方式：  
  
|nFlags|LpszNewItem 的解释|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|包含应用程序提供 32 位值，应用程序可以用来维护与菜单项关联的附加数据。 此 32 位的值是在应用程序**itemData**由提供的结构的成员[WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925)和[WM_DRAWITEM](http://msdn.microsoft.com/library/windows/desktop/bb775923)消息。 菜单项最初显示或更改时，会发送这些消息。|  
|**MF_STRING**|包含指向以 null 结尾的字符串的长指针。 这是默认解释。|  
|**MF_SEPARATOR**|`lpszNewItem` （不需要），则忽略参数。|  
  
 *pBmp*  
 指向`CBitmap`将用作菜单项的对象。  
  
### <a name="return-value"></a>返回值  
 如果该函数成功，则为非 0；否则为 0。  
  
### <a name="remarks"></a>备注  
 应用程序可以通过设置中的值指定菜单项的状态`nFlags`。  
  
 每当驻留在的菜单 （无论窗口会显示），一个窗口发生更改时，应用程序应调用`CWnd::DrawMenuBar`。  
  
 当`nIDNewItem`指定弹出菜单中，它将成为在插入的菜单的一部分。 如果该菜单将被销毁，插入菜单上也将被销毁。 应从分离插入的菜单`CMenu`对象以避免冲突。  
  
 如果多文档界面 (MDI) 子窗口最大化的活动点和应用程序将弹出菜单插入 MDI 应用程序的菜单通过调用此函数并指定**MF_BYPOSITION**插入标志，菜单一个位置距离剩余比预期。 这是因为活动的 MDI 子窗口的控件菜单插入 MDI 框架窗口的菜单栏的第一个位置。 若要正确放置菜单上，应用程序必须将 1 添加到否则将使用的位置值。 应用程序可以使用**WM_MDIGETACTIVE**消息，以确定当前处于活动状态的子窗口是否最大化。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]  
  
##  <a name="insertmenuitem"></a>CMenu::InsertMenuItem  
 在菜单中指定位置插入新菜单项。  
  
```  
BOOL InsertMenuItem(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>参数  
 `uItem`  
 请参阅说明`uItem`中[InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988) Windows SDK 中。  
  
 `lpMenuItemInfo`  
 请参阅说明`lpmii`中**InsertMenuItem** Windows SDK 中。  
  
 `fByPos`  
 请参阅说明`fByPosition`中**InsertMenuItem** Windows SDK 中。  
  
### <a name="remarks"></a>备注  
 此函数包装[InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988)、 Windows SDK 中所述。  
  
##  <a name="loadmenu"></a>CMenu::LoadMenu  
 从应用程序的可执行文件中加载的菜单资源，并将其附加到`CMenu`对象。  
  
```  
BOOL LoadMenu(LPCTSTR lpszResourceName);  
BOOL LoadMenu(UINT nIDResource);
```  
  
### <a name="parameters"></a>参数  
 `lpszResourceName`  
 指向以 null 结尾的字符串，其中包含要加载的菜单资源名称。  
  
 `nIDResource`  
 指定要加载该菜单资源的菜单 ID。  
  
### <a name="return-value"></a>返回值  
 如果成功，则加载该菜单资源则不为否则为 0。  
  
### <a name="remarks"></a>备注  
 在退出之前, 应用程序必须释放系统资源与菜单关联，如果菜单未分配给一个窗口。 应用程序通过调用释放菜单[DestroyMenu](#destroymenu)成员函数。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]  
  
##  <a name="loadmenuindirect"></a>CMenu::LoadMenuIndirect  
 从内存中的菜单模板加载资源并将其附加到`CMenu`对象。  
  
```  
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```  
  
### <a name="parameters"></a>参数  
 *lpMenuTemplate*  
 指向菜单模板 (即单个[MENUITEMTEMPLATEHEADER](http://msdn.microsoft.com/library/windows/desktop/ms647583)结构和一个或多个集合[MENUITEMTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms647581)结构)。 有关这些两个结构的详细信息，请参阅 Windows SDK。  
  
### <a name="return-value"></a>返回值  
 如果成功，则加载该菜单资源则不为否则为 0。  
  
### <a name="remarks"></a>备注  
 菜单模板是标题后跟一个或多个集合[MENUITEMTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms647581)结构，其中每个可能包含一个或多个菜单项和弹出菜单。  
  
 版本号应为 0。  
  
 **MtOption**标志应包括**MF_END**弹出列表中的最后一项和主列表中的最后一项。 请参阅`AppendMenu`其他标志的成员函数。 **MtId**成员必须省略从**MENUITEMTEMPLATE**结构时**MF_POPUP**中指定**mtOption**。  
  
 为分配的空间**MENUITEMTEMPLATE**结构必须足够大小以容纳**mtString**以包含菜单项以 null 结尾的字符串的名称。  
  
 在退出之前, 应用程序必须释放系统资源与菜单关联，如果菜单未分配给一个窗口。 应用程序通过调用释放菜单[DestroyMenu](#destroymenu)成员函数。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]  
  
##  <a name="m_hmenu"></a>CMenu::m_hMenu  
 指定`HMENU`窗口菜单的句柄附加到`CMenu`对象。  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::LoadMenu](#loadmenu)。  
  
##  <a name="measureitem"></a>CMenu::MeasureItem  
 创建一个带所有者绘制样式的菜单时由框架调用。  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>参数  
 `lpMeasureItemStruct`  
 指向的指针`MEASUREITEMSTRUCT`结构。  
  
### <a name="remarks"></a>备注  
 默认情况下，此成员函数没有任何影响。 重写该成员函数，并填写`MEASUREITEMSTRUCT`结构以通知 Windows 菜单的维度。  
  
 请参阅[CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)有关的说明`MEASUREITEMSTRUCT`结构。  
  
### <a name="example"></a>示例  
 下面的代码是从 MFC [CTRLTEST](../../visual-cpp-samples.md)示例：  
  
 [!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]  
  
##  <a name="modifymenu"></a>CMenu::ModifyMenu  
 更改指定的位置处的现有菜单项`nPosition`。  
  
```  
BOOL ModifyMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL ModifyMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>参数  
 `nPosition`  
 指定要更改的菜单项。 `nFlags`参数可以用于解释`nPosition`通过以下方式：  
  
|nFlags|NPosition 的解释|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|指定参数提供的命令 ID 的现有的菜单项。 这是默认值，如果既没有**MF_BYCOMMAND**也不**MF_BYPOSITION**设置。|  
|**MF_BYPOSITION**|指定参数提供现有的菜单项的位置。 第一项位于位置 0。|  
  
 `nFlags`  
 指定如何`nPosition`解释，并提供有关必须对菜单项所做的更改的信息。 可以设置的标志的列表，请参阅[AppendMenu](#appendmenu)成员函数。  
  
 `nIDNewItem`  
 指定修改后的菜单项的命令 ID 或者，如果`nFlags`设置为**MF_POPUP**，菜单句柄 ( `HMENU`) 的弹出菜单。 `nIDNewItem`忽略参数 （不需要） 如果`nFlags`设置为**MF_SEPARATOR**。  
  
 `lpszNewItem`  
 指定新的菜单项的内容。 `nFlags`参数可以用于解释`lpszNewItem`通过以下方式：  
  
|nFlags|LpszNewItem 的解释|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|包含应用程序提供 32 位值，应用程序可以用来维护与菜单项关联的附加数据。 在处理时，此 32 位的值是应用程序**MF_MEASUREITEM**和**MF_DRAWITEM**。|  
|**MF_STRING**|包含的长指针到以 null 结尾的字符串或`CString`。|  
|**MF_SEPARATOR**|`lpszNewItem` （不需要），则忽略参数。|  
  
 *pBmp*  
 指向`CBitmap`将用作菜单项的对象。  
  
### <a name="return-value"></a>返回值  
 如果该函数成功，则为非 0；否则为 0。  
  
### <a name="remarks"></a>备注  
 应用程序的设置中的值将指定菜单项的新状态`nFlags`。 如果此函数取代弹出菜单与菜单项关联，它将销毁旧的弹出菜单和释放使用弹出菜单的内存。  
  
 当`nIDNewItem`指定弹出菜单中，它将成为在插入的菜单的一部分。 如果该菜单将被销毁，插入菜单上也将被销毁。 应从分离插入的菜单`CMenu`对象以避免冲突。  
  
 每当驻留在的菜单 （无论窗口会显示），一个窗口发生更改时，应用程序应调用`CWnd::DrawMenuBar`。 若要更改现有的菜单项的属性，是使用要快得多`CheckMenuItem`和`EnableMenuItem`成员函数。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::InsertMenu](#insertmenu)。  
  
##  <a name="operator_hmenu"></a>CMenu::operator HMENU  
 使用此运算符将检索的句柄`CMenu`对象。  
  
```  
operator HMENU() const;  
```  
  
### <a name="return-value"></a>返回值  
 如果成功的句柄`CMenu`对象; 否则为**NULL**。  
  
### <a name="remarks"></a>备注  
 句柄可用于直接调用 Windows Api。  
  
##  <a name="operator_neq"></a>CMenu::operator ！ =  
 确定两个菜单是否逻辑上不相等。  
  
```  
BOOL operator!=(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>参数  
 `menu`  
 A`CMenu`比较的对象。  
  
### <a name="remarks"></a>备注  
 测试在左侧的菜单对象是否不等于右侧的菜单对象。  
  
##  <a name="operator_eq_eq"></a>CMenu::operator = =  
 确定两个菜单是否逻辑上相等。  
  
```  
BOOL operator==(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>参数  
 `menu`  
 A`CMenu`比较的对象。  
  
### <a name="remarks"></a>备注  
 测试在左侧的菜单对象是否相等 (方面`HMENU`值) 到右侧上的菜单对象。  
  
##  <a name="removemenu"></a>CMenu::RemoveMenu  
 从菜单中删除具有关联的弹出菜单的菜单项。  
  
```  
BOOL RemoveMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>参数  
 `nPosition`  
 指定要删除的菜单项。 `nFlags`参数可以用于解释`nPosition`通过以下方式：  
  
|nFlags|NPosition 的解释|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|指定参数提供的命令 ID 的现有的菜单项。 这是默认值，如果既没有**MF_BYCOMMAND**也不**MF_BYPOSITION**设置。|  
|**MF_BYPOSITION**|指定参数提供现有的菜单项的位置。 第一项位于位置 0。|  
  
 `nFlags`  
 指定如何`nPosition`解释。  
  
### <a name="return-value"></a>返回值  
 如果该函数成功，则为非 0；否则为 0。  
  
### <a name="remarks"></a>备注  
 它不会销毁弹出菜单的句柄，以便可以重用菜单。 在调用此函数时之前, 应用程序可能调用`GetSubMenu`成员函数来检索弹出窗口`CMenu`以供重复使用的对象。  
  
 每当驻留在的菜单 （无论窗口会显示），一个窗口发生更改时，应用程序必须调用`CWnd::DrawMenuBar`。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::InsertMenu](#insertmenu)。  
  
##  <a name="setdefaultitem"></a>CMenu::SetDefaultItem  
 将指定菜单默认菜单项设置。  
  
```  
BOOL SetDefaultItem(
    UINT uItem,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>参数  
 `uItem`  
 标识符或新的默认菜单项或-1 表示没有默认的项目的位置。 此参数的含义取决于值`fByPos`。  
  
 `fByPos`  
 值，该值指定的含义`uItem`。 如果此参数为**FALSE**，`uItem`是菜单项标识符。 否则，它是菜单项位置。  
  
### <a name="return-value"></a>返回值  
 如果函数成功，则返回值不为零。 如果函数失败，则返回值为零。 若要获得扩展的错误信息，请使用 Win32 函数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)，如 Windows SDK 中所述。  
  
### <a name="remarks"></a>备注  
 此成员函数实现的 Win32 函数的行为[SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996)，如 Windows SDK 中所述。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::InsertMenu](#insertmenu)。  
  
##  <a name="setmenucontexthelpid"></a>CMenu::SetMenuContextHelpId  
 将使用上下文帮助 ID 相关联`CMenu`。  
  
```  
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```  
  
### <a name="parameters"></a>参数  
 `dwContextHelpId`  
 要将与相关联的上下文帮助 ID `CMenu`。  
  
### <a name="return-value"></a>返回值  
 如果成功，则非零否则为 0  
  
### <a name="remarks"></a>备注  
 在菜单中的所有项都共享此标识符，不能附加到各个菜单项的帮助上下文标识符。  
  
### <a name="example"></a>示例  
  请参阅示例[CMenu::InsertMenu](#insertmenu)。  
  
##  <a name="setmenuinfo"></a>CMenu::SetMenuInfo  
 设置为菜单的信息。  
  
```  
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```  
  
### <a name="parameters"></a>参数  
 `lpcmi`  
 指向的指针[MENUINFO](http://msdn.microsoft.com/library/windows/desktop/ms647575)结构，它包含菜单上的信息。  
  
### <a name="return-value"></a>返回值  
 如果函数成功，返回值为非零值;否则，返回值为零。  
  
### <a name="remarks"></a>备注  
 调用此函数可设置有关菜单上的特定信息。  
  
##  <a name="setmenuitembitmaps"></a>CMenu::SetMenuItemBitmaps  
 将指定的位图与菜单项相关联。  
  
```  
BOOL SetMenuItemBitmaps(
    UINT nPosition,  
    UINT nFlags,  
    const CBitmap* pBmpUnchecked,  
    const CBitmap* pBmpChecked);
```  
  
### <a name="parameters"></a>参数  
 `nPosition`  
 指定要更改的菜单项。 `nFlags`参数可以用于解释`nPosition`通过以下方式：  
  
|nFlags|NPosition 的解释|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|指定参数提供的命令 ID 的现有的菜单项。 这是默认值，如果既没有**MF_BYCOMMAND**也不**MF_BYPOSITION**设置。|  
|**MF_BYPOSITION**|指定参数提供现有的菜单项的位置。 第一项位于位置 0。|  
  
 `nFlags`  
 指定如何`nPosition`解释。  
  
 `pBmpUnchecked`  
 指定要使用适用于未选中的菜单项的位图。  
  
 `pBmpChecked`  
 指定要用于选中的菜单项的位图。  
  
### <a name="return-value"></a>返回值  
 如果该函数成功，则为非 0；否则为 0。  
  
### <a name="remarks"></a>备注  
 选中或取消选中菜单项是否，Windows 将显示菜单项旁边的相应位图。  
  
 如果任一`pBmpUnchecked`或`pBmpChecked`是**NULL**，则 Windows 将显示相应的属性的菜单项旁边的执行任何操作。 如果两个参数均**NULL**，在项被选中且未选中的项时移除复选标记时，Windows 将使用默认复选标记。  
  
 菜单已销毁时，将不会销毁这些位图;应用程序必须将其销毁。  
  
 Windows **GetMenuCheckMarkDimensions**函数将检索默认复选标记用于菜单项的尺寸。 应用程序使用这些值来确定使用此函数提供的位图的适当大小。 获取的大小，创建你的位图，然后将其设置。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]  
  
##  <a name="setmenuiteminfo"></a>CMenu::SetMenuItemInfo  
 更改菜单项有关的信息。  
  
```  
BOOL SetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>参数  
 `uItem`  
 请参阅说明`uItem`中[SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001) Windows SDK 中。  
  
 `lpMenuItemInfo`  
 请参阅说明`lpmii`中**SetMenuItemInfo** Windows SDK 中。  
  
 `fByPos`  
 请参阅说明`fByPosition`中**SetMenuItemInfo** Windows SDK 中。  
  
### <a name="remarks"></a>备注  
 此函数包装[SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001)、 Windows SDK 中所述。  
  
##  <a name="trackpopupmenu"></a>CMenu::TrackPopupMenu  
 在指定位置显示浮动的弹出菜单，并在弹出菜单上跟踪选定的项。  
  
```  
BOOL TrackPopupMenu(
    UINT nFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPCRECT lpRect = 0);
```  
  
### <a name="parameters"></a>参数  
 `nFlags`  
 指定屏幕位置和鼠标位置的标志。 请参阅[TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002)有关可用标志的列表。  
  
 *x*  
 指定屏幕坐标中的弹出菜单的水平位置。 根据值`nFlags`参数，菜单可以为左对齐、 右对齐或居中相对于此位置。  
  
 *y*  
 在屏幕上指定菜单的顶部屏幕坐标的垂直位置。  
  
 `pWnd`  
 标识拥有的弹出菜单的窗口。 此参数不能为**NULL**，即使**TPM_NONOTIFY**指定标志。 此窗口接收所有**WM_COMMAND**从菜单的消息。 在 Windows 版本 3.1 和更高版本中，该窗口不会收到**WM_COMMAND**消息直到`TrackPopupMenu`返回。 在 Windows 3.0 中，该窗口才接收**WM_COMMAND**消息之前`TrackPopupMenu`返回。  
  
 `lpRect`  
 已忽略。  
  
### <a name="return-value"></a>返回值  
 此方法返回的结果调用[TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) Windows SDK 中。  
  
### <a name="remarks"></a>备注  
 浮动的弹出菜单可以出现在屏幕上的任意位置。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]  
  
##  <a name="trackpopupmenuex"></a>CMenu::TrackPopupMenuEx  
 在指定位置显示浮动的弹出菜单，并在弹出菜单上跟踪选定的项。  
  
```  
BOOL TrackPopupMenuEx(
    UINT fuFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPTPMPARAMS lptpm);
```  
  
### <a name="parameters"></a>参数  
 `fuFlags`  
 指定扩展菜单的各种功能。 所有值的列表和它们的含义，请参阅[TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003)。  
  
 *x*  
 指定屏幕坐标中的弹出菜单的水平位置。  
  
 *y*  
 在屏幕上指定菜单的顶部屏幕坐标的垂直位置。  
  
 `pWnd`  
 指向拥有的弹出菜单和菜单创建接收消息窗口的指针。 此窗口可以是从当前应用程序的任何窗口，但不能为**NULL**。 如果指定**TPM_NONOTIFY**中`fuFlags`参数，该函数不会发送到任何消息`pWnd`。 该函数必须返回指向对窗口`pWnd`接收**WM_COMMAND**消息。  
  
 *lptpm*  
 指向[TPMPARAMS](http://msdn.microsoft.com/library/windows/desktop/ms647586)结构，它指定屏幕菜单区域不应重叠。 此参数可以为**NULL**。  
  
### <a name="return-value"></a>返回值  
 如果指定**TPM_RETURNCMD**中`fuFlags`参数，返回值是用户选定的项的菜单项标识符。 如果用户取消菜单不做任何选择，或者如果发生错误，则返回值为 0。  
  
 如果不指定**TPM_RETURNCMD**中`fuFlags`参数，返回值表示非零，如果函数成功，0 失败。 若要获得扩展的错误信息，调用[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)。  
  
### <a name="remarks"></a>备注  
 浮动的弹出菜单可以出现在屏幕上的任意位置。 创建弹出菜单时处理错误的详细信息，请参阅[TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003)。  
  
## <a name="see-also"></a>请参阅  
 [MFC 示例 CTRLTEST](../../visual-cpp-samples.md)   
 [MFC 示例 DYNAMENU](../../visual-cpp-samples.md)   
 [CObject 类](../../mfc/reference/cobject-class.md)   
 [层次结构图](../../mfc/hierarchy-chart.md)   
 [CObject 类](../../mfc/reference/cobject-class.md)
