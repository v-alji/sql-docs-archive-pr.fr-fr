---
title: Implémentation des métadonnées externes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- disconnected validation [Integration Services]
- connected validation [Integration Services]
- custom data flow components [Integration Services], validating
- validation [Integration Services], components
- metadata [Integration Services]
- data flow components [Integration Services], validating
- data flow components [Integration Services], external metadata
- custom data flow components [Integration Services], external metadata
- external metadata [Integration Services]
ms.assetid: 8f5bd3ed-3e79-43a4-b6c1-435e4c2cc8cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a6b77229c528bc08057e662a4b3761d1daf732f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697023"
---
# <a name="implementing-external-metadata"></a><span data-ttu-id="254ea-102">Implémentation des métadonnées externes</span><span class="sxs-lookup"><span data-stu-id="254ea-102">Implementing External Metadata</span></span>
  <span data-ttu-id="254ea-103">Lorsqu'un composant est déconnecté de sa source de données, vous pouvez valider les colonnes comprises dans les collections de colonnes d'entrée et de sortie par rapport aux colonnes de sa source de données externe en utilisant l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100>.</span><span class="sxs-lookup"><span data-stu-id="254ea-103">When a component is disconnected from its data source, you can validate the columns in the input and output column collections against the columns at its external data source by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100> interface.</span></span> <span data-ttu-id="254ea-104">Cette interface vous permet de conserver un instantané des colonnes à la source de données externe et de les mapper aux colonnes de la collection de colonnes d'entrée et de sortie du composant.</span><span class="sxs-lookup"><span data-stu-id="254ea-104">This interface lets you maintain a snapshot of the columns at the external data source and map these columns to the columns in the input and output column collection of the component.</span></span>  
  
 <span data-ttu-id="254ea-105">L'implémentation de colonnes de métadonnées externes ajoute une couche de charge et de complexité au développement du composant, parce que vous devez effectuer une gestion et une validation par rapport à une collection de colonnes supplémentaire, mais la capacité d'éviter des allers-retours onéreux vers le serveur pour la validation peut rendre ce travail de développement valable.</span><span class="sxs-lookup"><span data-stu-id="254ea-105">Implementing external metadata columns adds a layer of overhead and complexity to component development, because you must maintain and validate against an additional column collection, but the ability to avoid expensive round trips to the server for validation may make this development work worthwhile.</span></span>  
  
## <a name="populating-external-metadata-columns"></a><span data-ttu-id="254ea-106">Remplissage de colonnes de métadonnées externes</span><span class="sxs-lookup"><span data-stu-id="254ea-106">Populating External Metadata Columns</span></span>  
 <span data-ttu-id="254ea-107">Les colonnes de métadonnées externes sont ajoutées en général à la collection lorsque la colonne d'entrée ou de sortie correspondante est créée.</span><span class="sxs-lookup"><span data-stu-id="254ea-107">External metadata columns are typically added to the collection when the corresponding input or output column is created.</span></span> <span data-ttu-id="254ea-108">Les nouvelles colonnes sont créées en appelant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.New%2A>.</span><span class="sxs-lookup"><span data-stu-id="254ea-108">New columns are created by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.New%2A> method.</span></span> <span data-ttu-id="254ea-109">Les propriétés de la colonne sont alors configurées pour correspondre à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="254ea-109">The properties of the column are then set to match the external data source.</span></span>  
  
 <span data-ttu-id="254ea-110">La colonne de métadonnées externes est mappée à la colonne d'entrée ou de sortie correspondante en assignant l'ID de la colonne de métadonnées externes à la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> de la colonne d'entrée ou de sortie.</span><span class="sxs-lookup"><span data-stu-id="254ea-110">The external metadata column is mapped to the corresponding input or output column by assigning the ID of the external metadata column to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> property of the input or output column.</span></span> <span data-ttu-id="254ea-111">Cela vous permet de localiser facilement la colonne de métadonnées externes pour une colonne d'entrée ou de sortie spécifique en utilisant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.GetObjectByID%2A> de la collection.</span><span class="sxs-lookup"><span data-stu-id="254ea-111">This lets you locate the external metadata column easily for a specific input or output column by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.GetObjectByID%2A> method of the collection.</span></span>  
  
 <span data-ttu-id="254ea-112">L'exemple suivant indique comment créer une colonne de métadonnées externes, puis comment la mapper à une colonne de sortie en définissant la propriété<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A>.</span><span class="sxs-lookup"><span data-stu-id="254ea-112">The following example shows how to create an external metadata column and then map the column to an output column by setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> property.</span></span>  
  
```csharp  
public void CreateExternalMetaDataColumn(IDTSOutput100 output, int outputColumnID )  
{  
    IDTSOutputColumn100 oColumn = output.OutputColumnCollection.GetObjectByID(outputColumnID);  
    IDTSExternalMetadataColumn100 eColumn = output.ExternalMetadataColumnCollection.New();  
  
    eColumn.DataType = oColumn.DataType;  
    eColumn.Precision = oColumn.Precision;  
    eColumn.Scale = oColumn.Scale;  
    eColumn.Length = oColumn.Length;  
    eColumn.CodePage = oColumn.CodePage;  
  
    oColumn.ExternalMetadataColumnID = eColumn.ID;  
}  
```  
  
```vb  
Public Sub CreateExternalMetaDataColumn(ByVal output As IDTSOutput100, ByVal outputColumnID As Integer)   
 Dim oColumn As IDTSOutputColumn100 = output.OutputColumnCollection.GetObjectByID(outputColumnID)   
 Dim eColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New   
 eColumn.DataType = oColumn.DataType   
 eColumn.Precision = oColumn.Precision   
 eColumn.Scale = oColumn.Scale   
 eColumn.Length = oColumn.Length   
 eColumn.CodePage = oColumn.CodePage   
 oColumn.ExternalMetadataColumnID = eColumn.ID   
End Sub  
```  
  
## <a name="validating-with-external-metadata-columns"></a><span data-ttu-id="254ea-113">Validation avec les colonnes de métadonnées externes</span><span class="sxs-lookup"><span data-stu-id="254ea-113">Validating with External Metadata Columns</span></span>  
 <span data-ttu-id="254ea-114">La validation requiert des étapes supplémentaires pour les composants qui gèrent une collection de colonnes de métadonnées externes, parce que vous devez effectuer une validation par rapport à une collection supplémentaire de colonnes.</span><span class="sxs-lookup"><span data-stu-id="254ea-114">Validation requires additional steps for components that maintain an external metadata column collection, because you must validate against an additional collection of columns.</span></span> <span data-ttu-id="254ea-115">La validation peut être divisée en validation connectée ou validation déconnectée.</span><span class="sxs-lookup"><span data-stu-id="254ea-115">Validation can be divided into connected validation or disconnected validation.</span></span>  
  
### <a name="connected-validation"></a><span data-ttu-id="254ea-116">Validation connectée</span><span class="sxs-lookup"><span data-stu-id="254ea-116">Connected Validation</span></span>  
 <span data-ttu-id="254ea-117">Lorsqu'un composant est connecté à une source de données externe, les colonnes comprises dans les collections d'entrée ou de sortie sont vérifiées directement par rapport à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="254ea-117">When a component is connected to an external data source, the columns in the input or output collections are verified directly against the external data source.</span></span> <span data-ttu-id="254ea-118">En outre, les colonnes comprises dans la collection de métadonnées externes doivent être validées.</span><span class="sxs-lookup"><span data-stu-id="254ea-118">Additionally, the columns in the external metadata collection must be validated.</span></span> <span data-ttu-id="254ea-119">Cette validation est requise car la collection de métadonnées externe peut être modifiée à l’aide de l’**Éditeur avancé** dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], et les modifications apportées à la collection ne sont pas détectables.</span><span class="sxs-lookup"><span data-stu-id="254ea-119">This is required because the external metadata collection can be modified by using the **Advanced Editor** in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], and changes made to the collection are not detectable.</span></span> <span data-ttu-id="254ea-120">Par conséquent, en cas de connexion, les composants doivent s'assurer que les colonnes comprises dans la collection de colonnes de métadonnées externes continuent à refléter les colonnes à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="254ea-120">Therefore, when connected, components must make sure that the columns in the external metadata column collection continue to reflect the columns at the external data source.</span></span>  
  
 <span data-ttu-id="254ea-121">Vous pouvez choisir de masquer la collection de métadonnées externes dans la **éditeur avancé** en affectant <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.IsUsed%2A> à la propriété de la collection la valeur `false` .</span><span class="sxs-lookup"><span data-stu-id="254ea-121">You may choose to hide the external metadata collection in the **Advanced Editor** by setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.IsUsed%2A> property of the collection to `false`.</span></span> <span data-ttu-id="254ea-122">Cependant, cela masque également l’onglet **Mappage de colonnes** de l’éditeur, lequel permet aux utilisateurs de mapper des colonnes de la collection d’entrée ou de sortie aux colonnes de la collection de colonnes de métadonnées externes.</span><span class="sxs-lookup"><span data-stu-id="254ea-122">However this also hides the **Column Mapping** tab of the editor, which lets users map columns from the input or output collection to the columns in the external metadata column collection.</span></span> <span data-ttu-id="254ea-123">La définition de cette propriété sur `false` n'empêche pas les développeurs de modifier la collection par programme, mais elle fournit un niveau de protection pour la collection de colonnes de métadonnées externes d'un composant qui est utilisé exclusivement dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="254ea-123">Setting this property to `false` does not prevent developers from programmatically modifying the collection, but it does provide a level of protection for the external metadata column collection of a component that is used exclusively in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="disconnected-validation"></a><span data-ttu-id="254ea-124">Validation déconnectée</span><span class="sxs-lookup"><span data-stu-id="254ea-124">Disconnected Validation</span></span>  
 <span data-ttu-id="254ea-125">Lorsqu'un composant est déconnecté d'une source de données externe, la validation est simplifiée parce que les colonnes comprises dans la collection d'entrée ou de sortie sont vérifiées directement par rapport aux colonnes de la collection de métadonnées externes et non pas par rapport à la source externe.</span><span class="sxs-lookup"><span data-stu-id="254ea-125">When a component is disconnected from an external data source, validation is simplified because the columns in the input or output collection are verified directly against the columns in the external metadata collection and not against the external source.</span></span> <span data-ttu-id="254ea-126">Un composant doit effectuer une validation déconnectée lorsque la connexion à sa source de données externe n'a pas été établie ou lorsque la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> a pour valeur `false`.</span><span class="sxs-lookup"><span data-stu-id="254ea-126">A component should perform disconnected validation when the connection to its external data source has not been established, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="254ea-127">L'exemple de code suivant montre l'implémentation d'un composant qui effectue la validation par rapport à sa collection de colonnes de métadonnées externes.</span><span class="sxs-lookup"><span data-stu-id="254ea-127">The following code example demonstrates an implementation of a component that performs validation against its external metadata column collection.</span></span>  
  
```csharp  
public override DTSValidationStatus Validate()  
{  
    if( this.isConnected && ComponentMetaData.ValidateExternalMetaData )  
    {  
        // TODO: Perform connected validation.  
    }  
    else  
    {  
        // TODO: Perform disconnected validation.  
    }  
}  
```  
  
```vb  
Public  Overrides Function Validate() As DTSValidationStatus   
 If Me.isConnected AndAlso ComponentMetaData.ValidateExternalMetaData Then   
  ' TODO: Perform connected validation.  
 Else   
  ' TODO: Perform disconnected validation.  
 End If   
End Function  
```  
  
<span data-ttu-id="254ea-128">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="254ea-128">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="254ea-129">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="254ea-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="254ea-130">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="254ea-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="254ea-131">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="254ea-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="254ea-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="254ea-132">See Also</span></span>  
 [<span data-ttu-id="254ea-133">Flux de données</span><span class="sxs-lookup"><span data-stu-id="254ea-133">Data Flow</span></span>](../../data-flow/data-flow.md)  
  
  
