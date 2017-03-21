---
title: "Creating Application Pages for SharePoint | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "SharePoint development in Visual Studio, Web pages"
  - "SharePoint development in Visual Studio, content pages"
  - "SharePoint development in Visual Studio, application pages"
  - "application pages [SharePoint development in Visual Studio], developing"
  - "application pages [SharePoint development in Visual Studio], creating"
ms.assetid: a6e97149-15dd-4bdb-8d75-3b53f886f76c
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Creating Application Pages for SharePoint
  An *application page* is an ASP.NET Web page that is designed for use in a SharePoint Web site. Application pages are a specialized type of ASP.NET page. The primary difference between an application page and a standard ASP.NET page is that an application page contains content that is merged with a SharePoint master page. A master page enables application pages to share the same appearance and behavior as other pages on a site.  
  
 Visual Studio enables you to design application pages by using a designer. The designer displays a content area for each content placeholder that is defined in a master page. You can design the application page by dragging controls to these content areas.  
  
## Application Pages  
 Application pages are shared across all sites on the server, whereas a site page is specific to one site. For more information, [SharePoint Page Types](http://go.microsoft.com/fwlink/?LinkID=211584).  
  
 By default, most of the pages that appear when you create a SharePoint site are site pages. A site page can be added to a SharePoint page library. Users can customize a site page by using tools such as SharePoint Designer. A site page can also host features such as dynamic Web Parts, and Web Part Zones.  
  
 Application pages cannot do these things. However an application page is the best type of page to create if you want the page to contain custom code. Although you can add custom code to a site page, the code stops running when the user customizes the page by using tools such as SharePoint Designer.  
  
> [!NOTE]  
>  Visual Studio does not provide templates that help you create site pages for a SharePoint site. For more information, see [SharePoint Page Types](http://go.microsoft.com/fwlink/?LinkID=211584).  
  
## Creating an Application Page  
 To create an application page, add an **Application Page** item to a SharePoint project. When you create an application page, Visual Studio adds the following folders to your project:  
  
|Folder|Description|  
|------------|-----------------|  
|Layouts|Maps to the _layouts virtual directory of the SharePoint file system.|  
|Layouts subfolder|Contains the files that make up the application page. By default, this folder has the same name as your project. You can rename this folder at any time. When you run the project, Visual Studio deploys this folder to the _layouts virtual directory of the SharePoint file system.|  
  
 Visual Studio adds the following files to your project:  
  
|File|Description|  
|----------|-----------------|  
|ASP.NET page file (.aspx)|Contains XML markup that defines the page.|  
|Application page code file|Contains code behind the application page. Add code that handles events to this file.|  
|Application page designer code file|Contains code that is generated by the designer. Do not directly edit this file.|  
  
## Designing and Debugging an Application Page  
 Design the contents of an application page by using the Visual Web Developer designer in Visual Studio. This designer appears when you open the application page in your project (by double-clicking it or by opening its shortcut menu and then choosing **Open**). For more information about how to use this designer, see [Visual Studio Web Development Content Map](http://msdn.microsoft.com/en-us/9c31f93b-c8fb-4599-9b14-6194ec8c7539).  
  
> [!NOTE]  
>  You can design the page only in the **Source** view of the designer. The **Design** view of the designer is disabled for application pages.  
  
 You can debug an application page just as you would debug other SharePoint project items in Visual Studio. When you start the Visual Studio debugger, Visual Studio opens the SharePoint site.  
  
 To view the application page, you must manually navigate to the location of the application page (for example: http://*Server_Name*/_layouts/*Project_Name*/ApplicationPage1.aspx).  
  
 For more information about how to debug SharePoint projects, see [Troubleshooting SharePoint Solutions](../sharepoint/troubleshooting-sharepoint-solutions.md).  
  
## Choosing a Master Page  
 By default, an **Application Page** item references the master page of the site that you are using to debug your project. That page is named v4.master and you can find it listed in the **Master Page Gallery** of the SharePoint site.  
  
 You can explicitly change which master page is used by the application page by setting the `MasterPageFile` attribute of the application `Page` element. (For example: `MasterPageFile="~/_layouts/applicationv4.master"`). In fact, you must set this attribute if dynamic master pages are not enabled on the SharePoint server. For more information about master pages in SharePoint, see [Master Pages](http://go.microsoft.com/fwlink/?LinkID=169281).  
  
## See Also  
 [SharePoint Foundation Development in Depth](http://go.microsoft.com/fwlink/?LinkID=182103)   
 [ASP.NET Web Pages Overview](../Topic/ASP.NET%20Web%20Forms%20Pages%20Overview.md)   
 [ASP.NET Web Page Syntax Overview](../Topic/ASP.NET%20Web%20Forms%20Page%20Syntax%20Overview.md)   
 [Programming ASP.NET Web Pages](http://msdn.microsoft.com/en-us/5626c661-8057-4de8-b658-c2e35ed4b4c9)  
  
  