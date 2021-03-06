---
title: "CPageSetupDialog 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPageSetupDialog
- AFXDLGS/CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CreatePrinterDC
- AFXDLGS/CPageSetupDialog::DoModal
- AFXDLGS/CPageSetupDialog::GetDeviceName
- AFXDLGS/CPageSetupDialog::GetDevMode
- AFXDLGS/CPageSetupDialog::GetDriverName
- AFXDLGS/CPageSetupDialog::GetMargins
- AFXDLGS/CPageSetupDialog::GetPaperSize
- AFXDLGS/CPageSetupDialog::GetPortName
- AFXDLGS/CPageSetupDialog::OnDrawPage
- AFXDLGS/CPageSetupDialog::PreDrawPage
- AFXDLGS/CPageSetupDialog::m_psd
dev_langs: C++
helpviewer_keywords:
- CPageSetupDialog [MFC], CPageSetupDialog
- CPageSetupDialog [MFC], CreatePrinterDC
- CPageSetupDialog [MFC], DoModal
- CPageSetupDialog [MFC], GetDeviceName
- CPageSetupDialog [MFC], GetDevMode
- CPageSetupDialog [MFC], GetDriverName
- CPageSetupDialog [MFC], GetMargins
- CPageSetupDialog [MFC], GetPaperSize
- CPageSetupDialog [MFC], GetPortName
- CPageSetupDialog [MFC], OnDrawPage
- CPageSetupDialog [MFC], PreDrawPage
- CPageSetupDialog [MFC], m_psd
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ca193c59c5d9c914f5bf8827601f389c546ea85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="cpagesetupdialog-class"></a>CPageSetupDialog 类
封装由 Windows 公共 OLE“页面设置”对话框提供的服务以及对于设置和修改打印边距的额外支持。  
  
## <a name="syntax"></a>语法  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|构造 `CPageSetupDialog` 对象。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|创建设备上下文进行打印。|  
|[CPageSetupDialog::DoModal](#domodal)|显示对话框中，并允许用户进行选择。|  
|[CPageSetupDialog::GetDeviceName](#getdevicename)|返回打印机的设备的名称。|  
|[CPageSetupDialog::GetDevMode](#getdevmode)|返回当前`DEVMODE`的打印机。|  
|[CPageSetupDialog::GetDriverName](#getdrivername)|返回使用打印机的驱动程序。|  
|[CPageSetupDialog::GetMargins](#getmargins)|返回打印机的当前边距的设置。|  
|[CPageSetupDialog::GetPaperSize](#getpapersize)|返回打印机纸张大小。|  
|[CPageSetupDialog::GetPortName](#getportname)|返回的输出端口名称。|  
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|由框架调用以呈现打印页的屏幕图像。|  
|[CPageSetupDialog::PreDrawPage](#predrawpage)|在呈现打印页的屏幕图像之前由框架调用。|  
  
### <a name="public-data-members"></a>公共数据成员  
  
|名称|描述|  
|----------|-----------------|  
|[CPageSetupDialog::m_psd](#m_psd)|用于自定义的结构`CPageSetupDialog`对象。|  
  
## <a name="remarks"></a>备注  
 此类旨在代替打印设置对话框。  
  
 若要使用`CPageSetupDialog`对象，请首先创建对象使用`CPageSetupDialog`构造函数。 一旦构造的对话框中，你可以设置或修改中的任何值`m_psd`数据成员，以初始化对话框的控件的值。 [M_psd](#m_psd)结构属于类型**PAGESETUPDLG**。  
  
 初始化对话框控件后, 调用`DoModal`成员函数，以显示对话框中，并允许用户选择打印选项。 `DoModal`返回用户是否选择确定 ( **IDOK**) 或取消 ( **IDCANCEL**) 按钮。  
  
 如果`DoModal`返回**IDOK**，您可以使用其中几`CPageSetupDialog`的成员函数或访问`m_psd`数据成员，以检索信息由用户的输入。  
  
> [!NOTE]
>  常见的 OLE 页面设置对话框关闭后，用户所做的任何更改将不保存由框架。 它是由应用程序本身以保存到永久位置，例如，应用程序的文档或应用程序类的成员从该对话框中的任何值。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## <a name="requirements"></a>惠?  
 **标头：** afxdlgs.h  
  
##  <a name="cpagesetupdialog"></a>CPageSetupDialog::CPageSetupDialog  
 调用此函数可构造`CPageSetupDialog`对象。  
  
```  
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>参数  
 `dwFlags`  
 可用于自定义的对话框中设置的一个或多个标志。 可以使用按位 OR 运算符组合的值。 这些值的含义如下：  
  
- **PSD_DEFAULTMINMARGINS**设置最小的允许宽度为页边距会作为打印机的最小值相同。 如果将忽略此标志**PSD_MARGINS**和**PSD_MINMARGINS**还指定标志。  
  
- **PSD_INWININIINTLMEASURE**未实现。  
  
- **PSD_MINMARGINS**会导致系统使用中指定的值**rtMinMargin**作为左、 顶部、 右侧和底部边距的最小允许宽度的成员。 系统会禁止用户输入不超过指定的最小宽度。 如果**PSD_MINMARGINS**未指定，则系统将允许的最小宽度设置为允许的打印机。  
  
- **PSD_MARGINS**激活边距控件区域。  
  
- **PSD_INTHOUSANDTHSOFINCHES**导致的对话框中的单元中英寸的 1/1000年测量。  
  
- **PSD_INHUNDREDTHSOFMILLIMETERS**导致对话框中的单元，1/100 毫米为单位测量。  
  
- **PSD_DISABLEMARGINS**禁用边距对话框控件。  
  
- **PSD_DISABLEPRINTER**禁用打印机按钮。  
  
- **PSD_NOWARNING**防止在没有任何默认打印机时显示警告消息。  
  
- **PSD_DISABLEORIENTATION**禁用页面方向对话框控件。  
  
- **PSD_RETURNDEFAULT**导致`CPageSetupDialog`返回[DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)和[DEVNAMES](../../mfc/reference/devnames-structure.md)而不显示对话框中的系统的默认打印机初始化的结构。 假定这两个**hDevNames**和**hDevMode**是**NULL**; 否则为函数将返回错误。 如果系统默认打印机支持的旧打印机驱动程序 （早于 Windows 版本 3.0），仅**hDevNames**返回;**hDevMode**是**NULL**。  
  
- **PSD_DISABLEPAPER**禁用纸选择控件。  
  
- **PSD_SHOWHELP**会使对话框以显示帮助按钮。 **HwndOwner**成员不得**NULL**如果指定此标志。  
  
- **PSD_ENABLEPAGESETUPHOOK**使中指定的挂钩函数**lpfnSetupHook**。  
  
- **PSD_ENABLEPAGESETUPTEMPLATE**会导致操作系统使用对话框模板中由标识创建对话框中**hInstance**和**lpSetupTemplateName**。  
  
- **PSD_ENABLEPAGESETUPTEMPLATEHANDLE**指示**hInstance**标识包含预加载的对话框模板的数据块。 系统将忽略**lpSetupTemplateName**如果指定此标志。  
  
- **PSD_ENABLEPAGEPAINTHOOK**使中指定的挂钩函数**lpfnPagePaintHook**。  
  
- **PSD_DISABLEPAGEPAINTING**禁用对话框中的绘图区域。  
  
 `pParentWnd`  
 对话框的父或所有者的指针。  
  
### <a name="remarks"></a>备注  
 使用[DoModal](../../mfc/reference/cdialog-class.md#domodal)函数来显示对话框。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>CPageSetupDialog::CreatePrinterDC  
 创建打印机设备上下文从[DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)和[DEVNAMES](../../mfc/reference/devnames-structure.md)结构。  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>返回值  
 新创建的打印机设备上下文 (DC) 的句柄。  
  
##  <a name="domodal"></a>CPageSetupDialog::DoModal  
 调用此函数可显示 Windows 公共 OLE 页面设置对话框，并让用户选择打印边距、 大小和方向的白皮书，和目标打印机等的各种打印设置选项。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>返回值  
 **IDOK**或**IDCANCEL**。 如果**IDCANCEL**是返回，调用 Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916)函数来确定是否发生了错误。  
  
 **IDOK**和**IDCANCEL**是指示用户是否选中确定或取消按钮的常量。  
  
### <a name="remarks"></a>备注  
 此外，用户可以访问网络位置和特定于选定的打印机的属性等的打印机安装选项。  
  
 如果你想要通过设置的成员初始化的各种页面设置对话框选项`m_psd`结构，应这样做，然后再调`DoModal`，并在构造对话框对象之后。 在调用`DoModal`，调用函数来检索设置或用户的信息输入到对话框中的其他成员。  
  
 如果你想要传播所输入的用户的当前设置，请调用[CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter)。 此函数采用中的信息`CPageSetupDialog`对象并初始化并选择新打印机 DC 具有正确的属性。  
  
 [!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]  
  
### <a name="example"></a>示例  
  请参阅示例[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)。  
  
##  <a name="getdevicename"></a>CPageSetupDialog::GetDeviceName  
 调用此函数后的`DoModal`来检索当前所选的打印机的名称。  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>返回值  
 使用的设备名称**CPageSetupDialog**对象。  
  
##  <a name="getdevmode"></a>CPageSetupDialog::GetDevMode  
 调用此函数在调用`DoModal`检索有关打印机设备上下文的信息`CPageSetupDialog`对象。  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>返回值  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)数据结构，其中包含有关设备初始化和打印驱动程序的环境的信息。 你必须首先解锁执行使用 Windows 此结构的内存[GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595)函数，Windows SDK 中所述。  
  
##  <a name="getdrivername"></a>CPageSetupDialog::GetDriverName  
 调用此函数在调用[DoModal](../../mfc/reference/cprintdialog-class.md#domodal)检索系统定义的打印机设备驱动程序的名称。  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>返回值  
 A`CString`指定系统定义的驱动程序名称。  
  
### <a name="remarks"></a>备注  
 使用指向指针`CString`返回对象`GetDriverName`的值作为`lpszDriverName`对的调用中[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)。  
  
##  <a name="getmargins"></a>CPageSetupDialog::GetMargins  
 在调用后调用此函数`DoModal`检索打印机设备驱动程序的边距。  
  
```  
void GetMargins(
    LPRECT lpRectMargins,  
    LPRECT lpRectMinMargins) const;  
```  
  
### <a name="parameters"></a>参数  
 *lpRectMargins*  
 指向[RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us)结构或[CRect](../../atl-mfc-shared/reference/crect-class.md)说明 （按 1/1000年英寸或 1/100 mm） 当前选定的打印机的打印边距的对象。 传递**NULL**为此参数，如果你不感兴趣此矩形。  
  
 *lpRectMinMargins*  
 指向`RECT`结构或`CRect`说明 （按 1/1000年英寸或 1/100 mm） 当前选定的打印机的最小打印边距的对象。 传递**NULL**为此参数，如果你不感兴趣此矩形。  
  
##  <a name="getpapersize"></a>CPageSetupDialog::GetPaperSize  
 调用此函数可检索用于打印选定的纸张大小。  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>返回值  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)对象，其中包含选定的用于打印 （在 1/1000年英寸或 1/100 mm） 纸张的大小。  
  
##  <a name="getportname"></a>CPageSetupDialog::GetPortName  
 调用此函数在调用`DoModal`检索当前所选的打印机端口的名称。  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>返回值  
 当前选定的打印机端口的名称。  
  
##  <a name="m_psd"></a>CPageSetupDialog::m_psd  
 类型的结构**PAGESETUPDLG**，其成员存储对话框对象的特征。  
  
```  
PAGESETUPDLG m_psd;  
```  
  
### <a name="remarks"></a>备注  
 后构造`CPageSetupDialog`对象时，可以使用`m_psd`设置对话框之前调用的各个方面`DoModal`成员函数。  
  
 如果你修改`m_psd`数据成员直接，您将重写任何默认行为。  
  
 有关详细信息[PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842)结构，请参阅 Windows SDK。  
  
 请参阅示例[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)。  
  
##  <a name="ondrawpage"></a>CPageSetupDialog::OnDrawPage  
 由框架调用以绘制打印页的屏幕图像。  
  
```  
virtual UINT OnDrawPage(
    CDC* pDC,  
    UINT nMessage,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>参数  
 `pDC`  
 指向打印机设备上下文的指针。  
  
 `nMessage`  
 指定一条消息，指出当前绘制页的区域。 可以是以下各项之一：  
  
- **WM_PSD_FULLPAGERECT**整个页面区域中。  
  
- **WM_PSD_MINMARGINRECT**当前最小的边距。  
  
- **WM_PSD_MARGINRECT**当前边距。  
  
- **WM_PSD_GREEKTEXTRECT**页面内容。  
  
- **WM_PSD_ENVSTAMPRECT**留待邮戳表示的区域。  
  
- **WM_PSD_YAFULLPAGERECT**的寄信人地址表示的区域。 此区域扩展到了示例页面区域中的边缘。  
  
 `lpRect`  
 指向[CRect](../../atl-mfc-shared/reference/crect-class.md)或[RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us)对象，其中包含的绘图区域的坐标。  
  
### <a name="return-value"></a>返回值  
 如果处理; 的非零值否则为 0。  
  
### <a name="remarks"></a>备注  
 此映像随后会显示为标准 OLE 页面设置对话框中的一部分。 默认实现绘制的文本页的图像。  
  
 重写此函数可自定义映像或整个图像的特定区域的绘制。 你可以执行此操作通过使用`switch`语句**用例**检查的值的语句`nMessage`。 例如，若要自定义的内容页图像的渲染，无法使用下面的代码示例：  
  
 [!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]  
  
 请注意，不需要处理的每个用例`nMessage`。 您可以选择处理映像的映像或整个区域的多个组件的一个组件。  
  
##  <a name="predrawpage"></a>CPageSetupDialog::PreDrawPage  
 在绘制打印页的屏幕图像之前由框架调用。  
  
```  
virtual UINT PreDrawPage(
    WORD wPaper,  
    WORD wFlags,  
    LPPAGESETUPDLG pPSD);
```  
  
### <a name="parameters"></a>参数  
 *wPaper*  
 指定一个值，指示纸张大小。 此值可以是之一**DMPAPER_**值中的说明列出[DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)结构。  
  
 `wFlags`  
 指示的方向的纸张或信封，并且打印机已点矩阵或 HPPCL （Hewlett Packard 打印机控件语言） 设备。 此参数可以具有下列值之一：  
  
-   0x001 纸张以横向模式 （圆点矩阵）  
  
-   0x003 纸张以横向模式 (HPPCL)  
  
-   0x005 纸张纵向模式下 （圆点矩阵）  
  
-   0x007 纸张纵向模式下 (HPPCL)  
  
-   0x00b 信封以横向模式 (HPPCL)  
  
-   0x00d 信封为纵向模式 （圆点矩阵）  
  
-   0x019 信封以横向模式 （圆点矩阵）  
  
-   0x01f 信封为纵向模式 （圆点矩阵）  
  
 `pPSD`  
 指向**PAGESETUPDLG**结构。 有关详细信息[PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842)，请参阅 Windows SDK。  
  
### <a name="return-value"></a>返回值  
 如果处理; 的非零值否则为 0。  
  
### <a name="remarks"></a>备注  
 重写此函数可自定义绘制图像。 如果你重写此函数并返回**TRUE**，你必须绘制整个图像。 如果你重写此函数并返回**FALSE**，由框架绘制整个默认图像。  
  
## <a name="see-also"></a>请参阅  
 [MFC 示例写字板](../../visual-cpp-samples.md)   
 [CCommonDialog 类](../../mfc/reference/ccommondialog-class.md)   
 [层次结构图](../../mfc/hierarchy-chart.md)



