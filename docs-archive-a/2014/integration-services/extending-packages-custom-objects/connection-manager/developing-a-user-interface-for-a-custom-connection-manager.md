---
title: Développement d’une interface utilisateur pour un gestionnaire de connexions personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], developing user interface
- custom user interface [Integration Services], custom connection manager
ms.assetid: 908bf2ac-fc84-4af8-a869-1cb43573d2df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc0e9f2a76f3d97c925c44219683ca6cd655e43f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604645"
---
# <a name="developing-a-user-interface-for-a-custom-connection-manager"></a><span data-ttu-id="e92d1-102">Développement d'une interface utilisateur pour un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="e92d1-102">Developing a User Interface for a Custom Connection Manager</span></span>
  <span data-ttu-id="e92d1-103">Après avoir remplacé l'implémentation des propriétés et méthodes de la classe de base afin de fournir vos fonctionnalités personnalisées, vous pouvez créer une interface utilisateur personnalisée pour votre gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="e92d1-103">After you have overridden the implementation of the properties and methods of the base class to provide your custom functionality, you may want to create a custom user interface for your connection manager.</span></span> <span data-ttu-id="e92d1-104">Si vous ne créez pas d'interface utilisateur personnalisée, les utilisateurs peuvent configurer votre gestionnaire de connexions uniquement en utilisant la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="e92d1-104">If you do not create a custom user interface, users can configure your connection manager only by using the Properties window.</span></span>  
  
 <span data-ttu-id="e92d1-105">Dans un projet d’interface utilisateur ou d’assembly personnalisé, vous avez normalement deux classes : une classe qui implémente l’objet <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> et le formulaire Windows qu’il affiche pour collecter des informations auprès de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e92d1-105">In a custom user interface project or assembly, you normally have two classes-a class that implements <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>, and the Windows form that it displays to gather information from the user.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e92d1-106">Après avoir signé et généré votre interface utilisateur personnalisée, puis l’avoir installée dans le Global Assembly Cache comme décrit dans [Codage d’un gestionnaire de connexions personnalisé](../building-deploying-and-debugging-custom-objects.md), n’oubliez pas de fournir le nom complet de cette classe dans la propriété <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> de la classe <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e92d1-106">After signing and building your custom user interface and installing it in the global assembly cache as described in [Coding a Custom Connection Manager](../building-deploying-and-debugging-custom-objects.md), remember to provide the fully qualified name of this class in the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e92d1-107">Une grande partie des tâches, sources et destinations intégrées à [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] utilisent uniquement des types spécifiques de gestionnaires de connexions intégrés.</span><span class="sxs-lookup"><span data-stu-id="e92d1-107">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="e92d1-108">Par conséquent, ces exemples ne peuvent pas être testés avec les tâches et composants intégrés.</span><span class="sxs-lookup"><span data-stu-id="e92d1-108">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="coding-the-user-interface-class"></a><span data-ttu-id="e92d1-109">Codage de la classe d'interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e92d1-109">Coding the User Interface Class</span></span>  
 <span data-ttu-id="e92d1-110">L'interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> comporte quatre méthodes : <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Delete%2A>.</span><span class="sxs-lookup"><span data-stu-id="e92d1-110">The <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> interface has four methods: <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Delete%2A>.</span></span> <span data-ttu-id="e92d1-111">Les sections suivantes décrivent ces quatre méthodes.</span><span class="sxs-lookup"><span data-stu-id="e92d1-111">The following sections describe these four methods.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e92d1-112">Il se peut que vous n'ayez pas à écrire de code pour la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Delete%2A> si aucun nettoyage n'est requis lorsque l'utilisateur supprime une instance du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="e92d1-112">You may not need to write any code for the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Delete%2A> method if no cleanup is required when the user deletes an instance of the connection manager.</span></span>  
  
### <a name="initializing-the-user-interface"></a><span data-ttu-id="e92d1-113">Initialisation de l'interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e92d1-113">Initializing the User Interface</span></span>  
 <span data-ttu-id="e92d1-114">Dans la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A>, le concepteur fournit une référence au gestionnaire de connexions en cours de configuration afin que la classe d'interface utilisateur puisse modifier les propriétés du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="e92d1-114">In the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A> method, the designer provides a reference to the connection manager that is being configured so that the user interface class can modify the connection manager's properties.</span></span> <span data-ttu-id="e92d1-115">Comme indiqué dans le code suivant, votre code doit mettre en cache la référence au gestionnaire de connexions en vue d’une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="e92d1-115">As shown in the following code, your code needs to cache the reference to the connection managerfor later use.</span></span>  
  
```vb  
Public Sub Initialize(ByVal connectionManager As Microsoft.SqlServer.Dts.Runtime.ConnectionManager, ByVal serviceProvider As System.IServiceProvider) Implements Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize  
  
    _connectionManager = connectionManager  
    _serviceProvider = serviceProvider  
  
  End Sub  
```  
  
```csharp  
public void Initialize(Microsoft.SqlServer.Dts.Runtime.ConnectionManager connectionManager, System.IServiceProvider serviceProvider)  
{  
  
  _connectionManager = connectionManager;  
  _serviceProvider = serviceProvider;  
  
}  
```  
  
### <a name="creating-a-new-instance-of-the-user-interface"></a><span data-ttu-id="e92d1-116">Création d'une instance de l'interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e92d1-116">Creating a New Instance of the User Interface</span></span>  
 <span data-ttu-id="e92d1-117">La méthode <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>, qui n'est pas un constructeur, est appelée après la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A> lorsque l'utilisateur crée une nouvelle instance du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="e92d1-117">The <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A> method, which is not a constructor, is called after the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A> method when the user creates a new instance of the connection manager.</span></span> <span data-ttu-id="e92d1-118">Dans la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>, vous souhaitez généralement afficher le formulaire à modifier, à moins que l'utilisateur ait copié et collé un gestionnaire de connexions existant.</span><span class="sxs-lookup"><span data-stu-id="e92d1-118">In the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A> method, you usually want to display the form for editing, unless the user has copied and pasted an existing connection manager.</span></span> <span data-ttu-id="e92d1-119">Le code suivant illustre une implémentation de cette méthode.</span><span class="sxs-lookup"><span data-stu-id="e92d1-119">The following code shows an implementation of this method.</span></span>  
  
```vb  
Public Function [New](ByVal parentWindow As System.Windows.Forms.IWin32Window, ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, ByVal connectionUIArgs As Microsoft.SqlServer.Dts.Runtime.Design.ConnectionManagerUIArgs) As Boolean Implements Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New  
  
  Dim clipboardService As IDtsClipboardService  
  
  clipboardService = _  
    DirectCast(_serviceProvider.GetService(GetType(IDtsClipboardService)), IDtsClipboardService)  
  If Not clipboardService Is Nothing Then  
    ' If the connection manager has been copied and pasted, take no action.  
    If clipboardService.IsPasteActive Then  
      Return True  
    End If  
  End If  
  
  Return EditSqlConnection(parentWindow)  
  
End Function  
```  
  
```csharp  
public bool New(System.Windows.Forms.IWin32Window parentWindow, Microsoft.SqlServer.Dts.Runtime.Connections connections, Microsoft.SqlServer.Dts.Runtime.Design.ConnectionManagerUIArgs connectionUIArgs)  
  {  
    IDtsClipboardService clipboardService;  
  
    clipboardService = (IDtsClipboardService)_serviceProvider.GetService(typeof(IDtsClipboardService));  
    if (clipboardService != null)  
    // If connection manager has been copied and pasted, take no action.  
    {  
      if (clipboardService.IsPasteActive)  
      {  
        return true;  
      }  
    }  
  
    return EditSqlConnection(parentWindow);  
  }  
```  
  
### <a name="editing-the-connection-manager"></a><span data-ttu-id="e92d1-120">Modification du gestionnaire de connexions</span><span class="sxs-lookup"><span data-stu-id="e92d1-120">Editing the Connection Manager</span></span>  
 <span data-ttu-id="e92d1-121">Étant donné que le formulaire de modification est appelé à la fois à partir des méthodes <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A>, il est plus pratique d'utiliser une fonction d'assistance pour encapsuler le code qui permet d'afficher le formulaire.</span><span class="sxs-lookup"><span data-stu-id="e92d1-121">Because the form for editing is called from both the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> methods, it is convenient to use a helper function to encapsulate the code that displays the form.</span></span> <span data-ttu-id="e92d1-122">Le code suivant illustre une implémentation de cette fonction d'assistance.</span><span class="sxs-lookup"><span data-stu-id="e92d1-122">The following code shows an implementation of this helper function.</span></span>  
  
```vb  
Private Function EditSqlConnection(ByVal parentWindow As IWin32Window) As Boolean  
  
  Dim sqlCMUIForm As New SqlConnMgrUIFormVB  
  
  sqlCMUIForm.Initialize(_connectionManager, _serviceProvider)  
  If sqlCMUIForm.ShowDialog(parentWindow) = DialogResult.OK Then  
    Return True  
  Else  
    Return False  
  End If  
  
End Function  
```  
  
```csharp  
private bool EditSqlConnection(IWin32Window parentWindow)  
 {  
  
   SqlConnMgrUIFormCS sqlCMUIForm = new SqlConnMgrUIFormCS();  
  
   sqlCMUIForm.Initialize(_connectionManager, _serviceProvider);  
   if (sqlCMUIForm.ShowDialog(parentWindow) == DialogResult.OK)  
   {  
     return true;  
   }  
   else  
   {  
     return false;  
   }  
  
 }  
```  
  
 <span data-ttu-id="e92d1-123">Dans la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A>, vous devez simplement afficher le formulaire à modifier.</span><span class="sxs-lookup"><span data-stu-id="e92d1-123">In the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> method, you simply have to display the form for editing.</span></span> <span data-ttu-id="e92d1-124">Le code suivant illustre une implémentation de la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> qui utilise une fonction d'assistance pour encapsuler le code pour le formulaire.</span><span class="sxs-lookup"><span data-stu-id="e92d1-124">The following code shows an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> method that uses a helper function to encapsulate the code for the form.</span></span>  
  
```vb  
Public Function Edit(ByVal parentWindow As System.Windows.Forms.IWin32Window, ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, ByVal connectionUIArg As Microsoft.SqlServer.Dts.Runtime.Design.ConnectionManagerUIArgs) As Boolean Implements Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit  
  
  Return EditSqlConnection(parentWindow)  
  
End Function  
```  
  
```csharp  
public bool Edit(System.Windows.Forms.IWin32Window parentWindow, Microsoft.SqlServer.Dts.Runtime.Connections connections, Microsoft.SqlServer.Dts.Runtime.Design.ConnectionManagerUIArgs connectionUIArg)  
{  
  
  return EditSqlConnection(parentWindow);  
  
}  
```  
  
## <a name="coding-the-user-interface-form"></a><span data-ttu-id="e92d1-125">Codage du formulaire d'interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e92d1-125">Coding the User Interface Form</span></span>  
 <span data-ttu-id="e92d1-126">Après avoir créé la classe d'interface utilisateur qui implémente les méthodes de l'interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>, vous devez créer un formulaire Windows où l'utilisateur peut configurer les propriétés de votre gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="e92d1-126">After creating the user interface class that implements the methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> interface, you must create a Windows form where the user can configure the properties of your connection manager.</span></span>  
  
### <a name="initializing-the-user-interface-form"></a><span data-ttu-id="e92d1-127">Initialisation du formulaire d'interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e92d1-127">Initializing the User Interface Form</span></span>  
 <span data-ttu-id="e92d1-128">Lorsque vous affichez votre formulaire personnalisé à modifier, vous pouvez passer une référence au gestionnaire de connexions modifié.</span><span class="sxs-lookup"><span data-stu-id="e92d1-128">When you display your custom form for editing, you can pass a reference to the connection manager that is being edited.</span></span> <span data-ttu-id="e92d1-129">Vous pouvez passer cette référence soit en utilisant un constructeur personnalisé pour la classe Form, soit en créant votre propre méthode `Initialize` comme illustré ici.</span><span class="sxs-lookup"><span data-stu-id="e92d1-129">You can pass this reference either by using a custom constructor for the form class, or by creating your own `Initialize` method as shown here.</span></span>  
  
```vb  
Public Sub Initialize(ByVal connectionManager As ConnectionManager, ByVal serviceProvider As IServiceProvider)  
  
  _connectionManager = connectionManager  
  _serviceProvider = serviceProvider  
  ConfigureControlsFromConnectionManager()  
  EnableControls()  
  
End Sub  
```  
  
```csharp  
public void Initialize(ConnectionManager connectionManager, IServiceProvider serviceProvider)  
 {  
  
   _connectionManager = connectionManager;  
   _serviceProvider = serviceProvider;  
   ConfigureControlsFromConnectionManager();  
   EnableControls();  
  
 }  
```  
  
### <a name="setting-properties-on-the-user-interface-form"></a><span data-ttu-id="e92d1-130">Définition de propriétés sur le formulaire d'interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e92d1-130">Setting Properties on the User Interface Form</span></span>  
 <span data-ttu-id="e92d1-131">Enfin, votre classe Form a besoin d'une fonction d'assistance qui permet de remplir les contrôles sur le formulaire lorsqu'il est tout d'abord chargé avec les valeurs existantes ou par défaut des propriétés du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="e92d1-131">Finally, your form class needs a helper function that populates the controls on the form when it is first loaded with the existing or the default values of the properties of the connection manager.</span></span> <span data-ttu-id="e92d1-132">Votre classe Form a également besoin d'une fonction similaire qui définit les valeurs des propriétés sur les valeurs entrées par l'utilisateur lorsqu'il clique sur OK et ferme le formulaire.</span><span class="sxs-lookup"><span data-stu-id="e92d1-132">Your form class also needs a similar function that sets the values of the properties to the values entered by the user when the user clicks OK and closes the form.</span></span>  
  
```vb  
Private Const CONNECTIONNAME_BASE As String = "SqlConnectionManager"  
  
Private Sub ConfigureControlsFromConnectionManager()  
  
  Dim tempName As String  
  Dim tempServerName As String  
  Dim tempDatabaseName As String  
  
  With _connectionManager  
  
    tempName = .Properties("Name").GetValue(_connectionManager).ToString  
    If Not String.IsNullOrEmpty(tempName) Then  
      _connectionName = tempName  
    Else  
      _connectionName = CONNECTIONNAME_BASE  
    End If  
  
    tempServerName = .Properties("ServerName").GetValue(_connectionManager).ToString  
    If Not String.IsNullOrEmpty(tempServerName) Then  
      _serverName = tempServerName  
      txtServerName.Text = _serverName  
    End If  
  
    tempDatabaseName = .Properties("DatabaseName").GetValue(_connectionManager).ToString  
    If Not String.IsNullOrEmpty(tempDatabaseName) Then  
      _databaseName = tempDatabaseName  
      txtDatabaseName.Text = _databaseName  
    End If  
  
  End With  
  
End Sub  
  
Private Sub ConfigureConnectionManagerFromControls()  
  
  With _connectionManager  
    .Properties("Name").SetValue(_connectionManager, _connectionName)  
    .Properties("ServerName").SetValue(_connectionManager, _serverName)  
    .Properties("DatabaseName").SetValue(_connectionManager, _databaseName)  
  End With  
  
End Sub  
```  
  
```csharp  
private const string CONNECTIONNAME_BASE = "SqlConnectionManager";  
  
private void ConfigureControlsFromConnectionManager()  
 {  
  
   string tempName;  
   string tempServerName;  
   string tempDatabaseName;  
  
   {  
     tempName = _connectionManager.Properties["Name"].GetValue(_connectionManager).ToString();  
     if (!String.IsNullOrEmpty(tempName))  
     {  
       _connectionName = tempName;  
     }  
     else  
     {  
       _connectionName = CONNECTIONNAME_BASE;  
     }  
  
     tempServerName = _connectionManager.Properties["ServerName"].GetValue(_connectionManager).ToString();  
     if (!String.IsNullOrEmpty(tempServerName))  
     {  
       _serverName = tempServerName;  
       txtServerName.Text = _serverName;  
     }  
  
     tempDatabaseName = _connectionManager.Properties["DatabaseName"].GetValue(_connectionManager).ToString();  
     if (!String.IsNullOrEmpty(tempDatabaseName))  
     {  
       _databaseName = tempDatabaseName;  
       txtDatabaseName.Text = _databaseName;  
     }  
  
   }  
  
 }  
  
 private void ConfigureConnectionManagerFromControls()  
 {  
  
   {  
     _connectionManager.Properties["Name"].SetValue(_connectionManager, _connectionName);  
     _connectionManager.Properties["ServerName"].SetValue(_connectionManager, _serverName);  
     _connectionManager.Properties["DatabaseName"].SetValue(_connectionManager, _databaseName);  
   }  
  
 }  
```  
  
<span data-ttu-id="e92d1-133">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e92d1-133">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e92d1-134">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="e92d1-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e92d1-135">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="e92d1-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e92d1-136">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="e92d1-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e92d1-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e92d1-137">See Also</span></span>  
 <span data-ttu-id="e92d1-138">[Création d’un gestionnaire de connexions personnalisé](creating-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e92d1-138">[Creating a Custom Connection Manager](creating-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="e92d1-139">Codage d'un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="e92d1-139">Coding a Custom Connection Manager</span></span>](coding-a-custom-connection-manager.md)  
  
  
