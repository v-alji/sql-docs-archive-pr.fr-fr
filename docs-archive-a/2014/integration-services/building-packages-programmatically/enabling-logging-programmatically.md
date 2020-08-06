---
title: Activation de la journalisation par programmation | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SQL Server Integration Services packages, logs
- SSIS packages, logs
- Integration Services packages, logs
- SSIS logging
- log providers [Integration Services]
- logs [Integration Services], enabling
- LoggingMode property
- LogProvider object
- packages [Integration Services], logs
ms.assetid: 3222a1ed-83eb-421c-b299-a53b67bba740
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ff7f81aca330960e4e94b0343080a37ded8c1273
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700152"
---
# <a name="enabling-logging-programmatically"></a><span data-ttu-id="673df-102">Activation de la journalisation par programme</span><span class="sxs-lookup"><span data-stu-id="673df-102">Enabling Logging Programmatically</span></span>
  <span data-ttu-id="673df-103">Le moteur d'exécution fournit une collection d'objets <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> qui permettent la capture d'informations spécifiques à un événement au cours de la validation et de l'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="673df-103">The run-time engine provides a collection of <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> objects that enable event-specific information to be captured during package validation and execution.</span></span> <span data-ttu-id="673df-104">Les objets <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> sont disponibles pour les objets <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer>, y compris les objets <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, <xref:Microsoft.SqlServer.Dts.Runtime.Package>, <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop> et <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>.</span><span class="sxs-lookup"><span data-stu-id="673df-104"><xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> objects are available to <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer> objects, including the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, <xref:Microsoft.SqlServer.Dts.Runtime.Package>, <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop>, and <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> objects.</span></span> <span data-ttu-id="673df-105">La journalisation est activée sur des conteneurs individuels, ou sur l'ensemble du package.</span><span class="sxs-lookup"><span data-stu-id="673df-105">Logging is enabled on individual containers, or on the whole package.</span></span>

 <span data-ttu-id="673df-106">Un conteneur peut utiliser plusieurs types des modules fournisseurs d'informations disponibles.</span><span class="sxs-lookup"><span data-stu-id="673df-106">There are several types of log providers that are available for a container to use.</span></span> <span data-ttu-id="673df-107">Il est donc possible de créer et stocker des informations de journal dans de multiples formats.</span><span class="sxs-lookup"><span data-stu-id="673df-107">This provides the flexibility to create and store log information in many formats.</span></span> <span data-ttu-id="673df-108">L'inscription d'un objet conteneur dans la journalisation s'effectue en deux étapes : d'abord l'activation de la journalisation, puis la sélection d'un module fournisseur d'informations.</span><span class="sxs-lookup"><span data-stu-id="673df-108">Enlisting a container object in logging is a two-step process: first logging is enabled, and then a log provider is selected.</span></span> <span data-ttu-id="673df-109">Les propriétés <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingOptions%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> du conteneur permettent de spécifier les événements enregistrés et sélectionner le module fournisseur d'informations.</span><span class="sxs-lookup"><span data-stu-id="673df-109">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingOptions%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> properties of the container are used to specify the logged events and to select the log provider.</span></span>

## <a name="enabling-logging"></a><span data-ttu-id="673df-110">Activation de la journalisation</span><span class="sxs-lookup"><span data-stu-id="673df-110">Enabling Logging</span></span>
 <span data-ttu-id="673df-111">La propriété <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A>, disponible dans chaque conteneur capable d'exécuter la journalisation, détermine si les informations d'événements du conteneur doivent être enregistrées dans le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="673df-111">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> property, found in each container that can perform logging, determines whether the container's event information is recorded to the event log.</span></span> <span data-ttu-id="673df-112">Cette propriété est affectée d'une valeur issue de la structure <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode> et est héritée du parent du conteneur par défaut.</span><span class="sxs-lookup"><span data-stu-id="673df-112">This property is assigned a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode> structure, and is inherited from the container's parent by default.</span></span> <span data-ttu-id="673df-113">Si le conteneur est un package, et n'a donc pas de parent, la propriété utilise <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode.UseParentSetting>, qui a comme valeur par défaut `Disabled`.</span><span class="sxs-lookup"><span data-stu-id="673df-113">If the container is a package, and therefore has no parent, the property uses the <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode.UseParentSetting>, which defaults to `Disabled`.</span></span>

### <a name="selecting-a-log-provider"></a><span data-ttu-id="673df-114">Sélection d'un module fournisseur d'informations</span><span class="sxs-lookup"><span data-stu-id="673df-114">Selecting a Log Provider</span></span>
 <span data-ttu-id="673df-115">Lorsque la propriété <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> a la valeur `Enabled`, un module fournisseur d'informations est ajouté à la collection <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> du conteneur pour terminer le processus.</span><span class="sxs-lookup"><span data-stu-id="673df-115">After the <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> property is set to `Enabled`, a log provider is added to the <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection of the container to complete the process.</span></span> <span data-ttu-id="673df-116">La collection <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> est disponible sur l'objet <xref:Microsoft.SqlServer.Dts.Runtime.LoggingOptions> et contient les modules fournisseurs d'informations sélectionnés pour le conteneur.</span><span class="sxs-lookup"><span data-stu-id="673df-116">The <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection is available on the <xref:Microsoft.SqlServer.Dts.Runtime.LoggingOptions> object, and contains the log providers selected for the container.</span></span> <span data-ttu-id="673df-117">La méthode <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders.Add%2A> est appelée pour créer un fournisseur et l'ajouter à la collection.</span><span class="sxs-lookup"><span data-stu-id="673df-117">The <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders.Add%2A> method is called to create a provider and add it to the collection.</span></span> <span data-ttu-id="673df-118">La méthode retourne ensuite le module fournisseur d'informations qui a été ajouté à la collection.</span><span class="sxs-lookup"><span data-stu-id="673df-118">The method then returns the log provider that was added to the collection.</span></span> <span data-ttu-id="673df-119">Chaque fournisseur a des paramètres de configuration spécifiques et ces propriétés sont définies à l'aide de la propriété <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="673df-119">Each provider has configuration settings that are unique to that provider, and these properties are set using the <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A> property.</span></span>

 <span data-ttu-id="673df-120">Le tableau suivant répertorie les modules fournisseurs d'informations disponibles, leur description et leurs informations <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="673df-120">The following table lists the available log providers, their description, and their <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A> information.</span></span>

|<span data-ttu-id="673df-121">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="673df-121">Provider</span></span>|<span data-ttu-id="673df-122">Description</span><span class="sxs-lookup"><span data-stu-id="673df-122">Description</span></span>|<span data-ttu-id="673df-123">Propriété ConfigString</span><span class="sxs-lookup"><span data-stu-id="673df-123">ConfigString property</span></span>|
|--------------|-----------------|---------------------------|
|<span data-ttu-id="673df-124">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="673df-124">SQL Server Profiler</span></span>|<span data-ttu-id="673df-125">Génère des traces SQL qui peuvent être capturées et affichées dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler.</span><span class="sxs-lookup"><span data-stu-id="673df-125">Generates SQL traces that may be captured and viewed in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler.</span></span> <span data-ttu-id="673df-126">L'extension de nom de fichier par défaut de ce fournisseur est .trc.</span><span class="sxs-lookup"><span data-stu-id="673df-126">The default file name extension for this provider is .trc.</span></span>|<span data-ttu-id="673df-127">Aucune configuration n'est requise.</span><span class="sxs-lookup"><span data-stu-id="673df-127">No configuration is required.</span></span>|
|<span data-ttu-id="673df-128">SQL Server</span><span class="sxs-lookup"><span data-stu-id="673df-128">SQL Server</span></span>|<span data-ttu-id="673df-129">Écrit les entrées du journal des événements dans la table **sysssislog** de toute base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="673df-129">Writes event log entries to the **sysssislog** table in any [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>|<span data-ttu-id="673df-130">Le fournisseur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requiert que la connexion à la base de données soit spécifiée, ainsi que le nom de la base de données cible.</span><span class="sxs-lookup"><span data-stu-id="673df-130">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider requires that the connection to the database be specified, and also the target database name.</span></span>|
|<span data-ttu-id="673df-131">Fichier texte</span><span class="sxs-lookup"><span data-stu-id="673df-131">Text File</span></span>|<span data-ttu-id="673df-132">Écrit les entrées du journal des événements dans des fichiers texte ASCII au format CSV.</span><span class="sxs-lookup"><span data-stu-id="673df-132">Writes event log entries to ASCII text files in a comma-separated value (CSV) format.</span></span> <span data-ttu-id="673df-133">L'extension de nom de fichier par défaut de ce fournisseur est .log.</span><span class="sxs-lookup"><span data-stu-id="673df-133">The default file name extension for this provider is .log.</span></span>|<span data-ttu-id="673df-134">Nom d'un gestionnaire de connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="673df-134">The name of a file connection manager.</span></span>|
|<span data-ttu-id="673df-135">Journal des événements Windows</span><span class="sxs-lookup"><span data-stu-id="673df-135">Windows Event Log</span></span>|<span data-ttu-id="673df-136">Enregistre dans le journal des événements Windows standard sur l'ordinateur local dans le journal des applications.</span><span class="sxs-lookup"><span data-stu-id="673df-136">Logs to standard Windows Event Log on the local computer in the Application log.</span></span>|<span data-ttu-id="673df-137">Aucune configuration n'est requise.</span><span class="sxs-lookup"><span data-stu-id="673df-137">No configuration is required.</span></span>|
|<span data-ttu-id="673df-138">Fichier XML</span><span class="sxs-lookup"><span data-stu-id="673df-138">XML File</span></span>|<span data-ttu-id="673df-139">Écrit les entrées du journal des événements dans un fichier au format XML.</span><span class="sxs-lookup"><span data-stu-id="673df-139">Writes event log entries to XML formatted file.</span></span> <span data-ttu-id="673df-140">L'extension de nom de fichier par défaut de ce fournisseur est .xml.</span><span class="sxs-lookup"><span data-stu-id="673df-140">The default file name extension for this provider is .xml</span></span>|<span data-ttu-id="673df-141">Nom d'un gestionnaire de connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="673df-141">The name of a file connection manager.</span></span>|

 <span data-ttu-id="673df-142">Les événements sont inclus dans le journal des événements, ou exclus de celui-ci, selon la définition des propriétés `EventFilterKind` et `EventFilter` du conteneur.</span><span class="sxs-lookup"><span data-stu-id="673df-142">Events are included in or excluded from the event log by setting the `EventFilterKind` and the `EventFilter` properties of the container.</span></span> <span data-ttu-id="673df-143">La structure `EventFilterKind` contient deux valeurs, `ExclusionFilter` et `InclusionFilter`, qui indiquent si les événements ajoutés à `EventFilter` sont inclus dans le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="673df-143">The `EventFilterKind` structure contains two values, `ExclusionFilter` and `InclusionFilter`, that indicate whether the events that are added to the `EventFilter` are included in the event log.</span></span> <span data-ttu-id="673df-144">Un tableau de chaînes qui contient les noms des événements faisant l'objet du filtrage est ensuite assigné à la propriété `EventFilter`.</span><span class="sxs-lookup"><span data-stu-id="673df-144">The `EventFilter` property is then assigned a string array that contains the names of the events that are the subject of the filtering.</span></span>

 <span data-ttu-id="673df-145">Le code suivant active la journalisation sur un package, ajoute le module fournisseur d'informations pour les fichiers texte à la collection <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> et spécifie une liste d'événements à inclure dans la sortie de la journalisation.</span><span class="sxs-lookup"><span data-stu-id="673df-145">The following code enables logging on a package, adds the log provider for Text files to the <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection, and specifies a list of events to include in the logging output.</span></span>

## <a name="sample"></a><span data-ttu-id="673df-146">Exemple</span><span class="sxs-lookup"><span data-stu-id="673df-146">Sample</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Package p = new Package();

      ConnectionManager loggingConnection = p.Connections.Add("FILE");
      loggingConnection.ConnectionString = @"C:\SSISPackageLog.txt";

      LogProvider provider = p.LogProviders.Add("DTS.LogProviderTextFile.2");
      provider.ConfigString = loggingConnection.Name;
      p.LoggingOptions.SelectedLogProviders.Add(provider);
      p.LoggingOptions.EventFilterKind = DTSEventFilterKind.Inclusion;
      p.LoggingOptions.EventFilter = new String[] { "OnPreExecute", 
         "OnPostExecute", "OnError", "OnWarning", "OnInformation" };
      p.LoggingMode = DTSLoggingMode.Enabled;

      // Add tasks and other objects to the package.

    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim p As Package = New Package()

    Dim loggingConnection As ConnectionManager = p.Connections.Add("FILE")
    loggingConnection.ConnectionString = "C:\SSISPackageLog.txt"

    Dim provider As LogProvider = p.LogProviders.Add("DTS.LogProviderTextFile.2")
    provider.ConfigString = loggingConnection.Name
    p.LoggingOptions.SelectedLogProviders.Add(provider)
    p.LoggingOptions.EventFilterKind = DTSEventFilterKind.Inclusion
    p.LoggingOptions.EventFilter = New String() {"OnPreExecute", _
       "OnPostExecute", "OnError", "OnWarning", "OnInformation"}
    p.LoggingMode = DTSLoggingMode.Enabled

    ' Add tasks and other objects to the package.

  End Sub

End Module
```

<span data-ttu-id="673df-147">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="673df-147">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="673df-148">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="673df-148">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="673df-149">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="673df-149">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="673df-150">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="673df-150">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="673df-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="673df-151">See Also</span></span>
 [<span data-ttu-id="673df-152">Journalisation Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="673df-152">Integration Services &#40;SSIS&#41; Logging</span></span>](../performance/integration-services-ssis-logging.md)


