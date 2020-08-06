---
title: Persistance des objets personnalisés | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom objects [Integration Services], persisting
ms.assetid: 97c19716-6447-4c1c-b277-cc2e6c1e6a6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 55baa48f1ab0cf4175592b095463c9f12293b83f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613549"
---
# <a name="persisting-custom-objects"></a><span data-ttu-id="fed84-102">Persistance des objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="fed84-102">Persisting Custom Objects</span></span>
  <span data-ttu-id="fed84-103">Il n'est pas nécessaire d'implémenter une persistance personnalisée pour les objets personnalisés que vous créez tant que leurs propriétés utilisent uniquement des types de données simples tels que les types `integer` et `string`.</span><span class="sxs-lookup"><span data-stu-id="fed84-103">You do not need to implement custom persistence for the custom objects that you create as long as their properties use only simple data types such as `integer` and `string`.</span></span> <span data-ttu-id="fed84-104">L'implémentation par défaut de la persistance enregistre les métadonnées de votre objet ainsi que les valeurs de toutes ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="fed84-104">The default implementation of persistence saves the metadata for your object along with the values of all its properties.</span></span>  
  
 <span data-ttu-id="fed84-105">Toutefois, si votre objet comporte des propriétés qui utilisent des types de données complexes, ou si vous souhaitez effectuer un traitement personnalisé sur des valeurs de propriétés lors de leur chargement et de leur enregistrement, vous pouvez implémenter l'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist> et ses méthodes <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist.LoadFromXML%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist.SaveToXML%2A>.</span><span class="sxs-lookup"><span data-stu-id="fed84-105">However, if your object has properties that use complex data types, or if you want to perform custom processing on property values as they are loaded and saved, you can implement the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist> interface and its <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist.LoadFromXML%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist.SaveToXML%2A> methods.</span></span> <span data-ttu-id="fed84-106">Avec ces méthodes, vous effectuez un chargement depuis (ou un enregistrement vers) la définition XML du package, d'un fragment XML qui contient les propriétés de votre objet et leurs valeurs actuelles.</span><span class="sxs-lookup"><span data-stu-id="fed84-106">In these methods you load from (or save to) the XML definition of the package an XML fragment that contains the properties of your object and their current values.</span></span> <span data-ttu-id="fed84-107">Le format de ce fragment XML n'est pas défini ; il doit uniquement s'agir d'un format XML bien formé.</span><span class="sxs-lookup"><span data-stu-id="fed84-107">The format of this XML fragment is not defined; it must only be well-formed XML.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fed84-108">Lorsque vous implémentez une persistance personnalisée, vous devez rendre persistantes toutes les propriétés de l'objet, y compris les propriétés héritées et les propriétés personnalisées que vous avez ajoutées.</span><span class="sxs-lookup"><span data-stu-id="fed84-108">When you implement custom persistence, you must persist all the properties of the object, including both inherited properties and custom properties that you have added.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fed84-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="fed84-109">Example</span></span>  
 <span data-ttu-id="fed84-110">Bien que l'exemple de gestionnaire de connexions personnalisé Sql Server ne requière pas de persistance personnalisée pour ses trois propriétés de type `string`, le code suivant présente un exemple du code personnalisé requis pour rendre persistants le gestionnaire de connexions et ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="fed84-110">Although the Sql Server Custom Connection Manager Sample does not require custom persistence for its three properties of type `string`, the following code shows an example of the custom code that would be required to persist the connection manager and its properties.</span></span> <span data-ttu-id="fed84-111">La classe qui contient ce code doit implémenter l'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist>.</span><span class="sxs-lookup"><span data-stu-id="fed84-111">The class that contains this code must implement the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist> interface.</span></span>  
  
```vb  
Private Const PERSIST_ELEMENT As String = "SqlConnectionManager"  
Private Const PERSIST_SERVER As String = "Server"  
Private Const PERSIST_DATABASE As String = "Database"  
Private Const PERSIST_CONNECTIONSTRING As String = "ConnectionString"  
  
Public Sub LoadFromXML(ByVal node As System.Xml.XmlElement, _  
  ByVal infoEvents As Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents) _  
  Implements Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist.LoadFromXML  
  
  Dim propertyNode As XmlNode  
  
  ' Make sure that the correct node is being loaded.  
  If node.Name <> PERSIST_ELEMENT Then  
    Throw New Exception("Persisted element is not of type " & PERSIST_ELEMENT)  
  End If  
  
  ' Load the three properties of the object from XML into variables.  
  For Each propertyNode In node.ChildNodes  
    Select Case propertyNode.Name  
      Case PERSIST_SERVER  
        _serverName = propertyNode.InnerText  
      Case PERSIST_DATABASE  
        _databaseName = propertyNode.InnerText  
      Case PERSIST_CONNECTIONSTRING  
        _connectionString = propertyNode.InnerText  
    End Select  
  Next  
  
End Sub  
  
Public Sub SaveToXML(ByVal doc As System.Xml.XmlDocument, _  
  ByVal infoEvents As Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents) _  
  Implements Microsoft.SqlServer.Dts.Runtime.IDTSComponentPersist.SaveToXML  
  
  Dim elementRoot As XmlElement  
  Dim propertyNode As XmlNode  
  
  ' Create a new node to persist the object and its properties.  
  elementRoot = doc.CreateElement(String.Empty, PERSIST_ELEMENT, String.Empty)  
  
  ' Save the three properties of the object from variables into XML.  
  propertyNode = doc.CreateNode(XmlNodeType.Element, PERSIST_SERVER, String.Empty)  
  propertyNode.InnerText = _serverName  
  elementRoot.AppendChild(propertyNode)  
  
  propertyNode = doc.CreateNode(XmlNodeType.Element, PERSIST_DATABASE, String.Empty)  
  propertyNode.InnerText = _databaseName  
  elementRoot.AppendChild(propertyNode)  
  
  propertyNode = doc.CreateNode(XmlNodeType.Element, PERSIST_CONNECTIONSTRING, String.Empty)  
  propertyNode.InnerText = _connectionString  
  elementRoot.AppendChild(propertyNode)  
  
  doc.AppendChild(elementRoot)  
  
End Sub  
```  
  
```csharp  
private const string PERSIST_ELEMENT = "SqlConnectionManager";  
private const string PERSIST_SERVER = "Server";  
private const string PERSIST_DATABASE = "Database";  
private const string PERSIST_CONNECTIONSTRING = "ConnectionString";  
  
public void LoadFromXML(System.Xml.XmlElement node,  
  Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents infoEvents)  
{  
  
  // Make sure that the correct node is being loaded.  
  if (node.Name != PERSIST_ELEMENT)  
  {  
    throw new Exception("Persisted element is not of type " + PERSIST_ELEMENT);  
  }  
  
  // Save the three properties of the object from variables into XML.  
  foreach (XmlNode propertyNode in node.ChildNodes)  
  {  
    switch (propertyNode.Name)  
    {  
      case PERSIST_SERVER:  
        _serverName = propertyNode.InnerText;  
        break;  
      case PERSIST_DATABASE:  
        _databaseName = propertyNode.InnerText;  
        break;  
      case PERSIST_CONNECTIONSTRING:  
        _connectionString = propertyNode.InnerText;  
        break;  
    }  
  }  
  
}  
  
public void SaveToXML(System.Xml.XmlDocument doc,  
  Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents infoEvents)  
{  
  
  XmlElement elementRoot;  
  XmlNode propertyNode;  
  
  // Create a new node to persist the object and its properties.  
  elementRoot = doc.CreateElement(String.Empty, PERSIST_ELEMENT, String.Empty);  
  
  // Save the three properties of the object from variables into XML.  
  propertyNode = doc.CreateNode(XmlNodeType.Element, PERSIST_SERVER, String.Empty);  
  propertyNode.InnerText = _serverName;  
  elementRoot.AppendChild(propertyNode);  
  
  propertyNode = doc.CreateNode(XmlNodeType.Element, PERSIST_DATABASE, String.Empty);  
  propertyNode.InnerText = _databaseName;  
  elementRoot.AppendChild(propertyNode);  
  
  propertyNode = doc.CreateNode(XmlNodeType.Element, PERSIST_CONNECTIONSTRING, String.Empty);  
  propertyNode.InnerText = _connectionString;  
  elementRoot.AppendChild(propertyNode);  
  
  doc.AppendChild(elementRoot);  
  
}  
```  
  
<span data-ttu-id="fed84-112">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="fed84-112">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="fed84-113">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="fed84-113">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="fed84-114">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="fed84-114">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="fed84-115">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="fed84-115">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed84-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fed84-116">See Also</span></span>  
 <span data-ttu-id="fed84-117">[Développement d’objets personnalisés pour Integration Services](developing-custom-objects-for-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="fed84-117">[Developing Custom Objects for Integration Services](developing-custom-objects-for-integration-services.md) </span></span>  
 [<span data-ttu-id="fed84-118">Génération, déploiement et débogage d’objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="fed84-118">Building, Deploying, and Debugging Custom Objects</span></span>](building-deploying-and-debugging-custom-objects.md)  
  
  
