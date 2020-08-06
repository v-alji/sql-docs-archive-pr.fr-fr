---
title: Configurer les paramètres avancés pour les fichiers journaux DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- log files,advanced settings
- dqs log files,advanced settings
ms.assetid: 1d565748-9759-425c-ae38-4d2032a86868
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ad41b0cac95f9bfe5565ccbac16b0fda3e28ddf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696096"
---
# <a name="configure-advanced-settings-for-dqs-log-files"></a><span data-ttu-id="7468f-102">Configurer les paramètres avancés pour les fichiers journaux DQS</span><span class="sxs-lookup"><span data-stu-id="7468f-102">Configure Advanced Settings for DQS Log Files</span></span>
  <span data-ttu-id="7468f-103">Cette rubrique explique comment configurer les paramètres avancés pour [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] et les fichiers journaux [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , tels que la définition de la limite de la taille des fichiers par progression des fichiers journaux, la définition du modèle d'horodatage les événements, etc.</span><span class="sxs-lookup"><span data-stu-id="7468f-103">This topic describes how to configure advanced settings for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log files, such as set the rolling file size limit of the log files, set the time stamp pattern of the events, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7468f-104">Ces activités ne peuvent pas être effectuées à l'aide de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]et sont réservées aux utilisateurs expérimentés uniquement.</span><span class="sxs-lookup"><span data-stu-id="7468f-104">These activities cannot be performed using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and is intended for advanced users only.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7468f-105">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="7468f-105">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7468f-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7468f-106">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7468f-107">Autorisations</span><span class="sxs-lookup"><span data-stu-id="7468f-107">Permissions</span></span>  
  
-   <span data-ttu-id="7468f-108">Votre compte d'utilisateur Windows doit être membre du rôle serveur fixe sysadmin dans l'instance SQL Server afin de pouvoir modifier les paramètres de configuration dans la table A_CONFIGURATION de la base de données DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="7468f-108">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance to modify configuration settings in the A_CONFIGURATION table in the DQS_MAIN database.</span></span>  
  
-   <span data-ttu-id="7468f-109">Vous devez être connecté en tant que membre du groupe Administrateurs sur l'ordinateur où vous modifiez le fichier DQLog.Client.xml pour configurer les paramètres de journalisation [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7468f-109">You must be logged on as a member of the Administrators group on the computer where you are modifying the DQLog.Client.xml file to configure the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] logging settings.</span></span>  
  
##  <a name="configure-data-quality-server-log-settings"></a><a name="DQSServer"></a> <span data-ttu-id="7468f-110">Configurer les paramètres des journaux du serveur de qualité des données</span><span class="sxs-lookup"><span data-stu-id="7468f-110">Configure Data Quality Server Log Settings</span></span>  
 <span data-ttu-id="7468f-111">Les paramètres des journaux [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] sont présents au format XML dans la colonne **VALUE** de la ligne **ServerLogging** de la table A_CONFIGURATION de la base de données DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="7468f-111">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log settings are present in an XML format in the **VALUE** column of the **ServerLogging** row in the A_CONFIGURATION table in the DQS_MAIN database.</span></span> <span data-ttu-id="7468f-112">Vous pouvez exécuter la requête SQL suivante pour afficher les informations de configuration :</span><span class="sxs-lookup"><span data-stu-id="7468f-112">You can run the following SQL query to view the configuration information:</span></span>  
  
```sql  
select * from DQS_MAIN.dbo.A_CONFIGURATION where NAME='ServerLogging'; 
```  
  
 <span data-ttu-id="7468f-113">Vous devez mettre à jour les informations appropriées dans la colonne **VALUE** de la ligne **ServerLogging** pour modifier les paramètres de configuration de la journalisation [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7468f-113">You must update the appropriate information in the **VALUE** column of the **ServerLogging** row to change the configuration settings for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging.</span></span> <span data-ttu-id="7468f-114">Dans cet exemple, nous mettrons à jour les paramètres des journaux [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] pour définir la limite de la taille des fichiers par progression à 25 000 Ko (valeur par défaut 20 000 Ko).</span><span class="sxs-lookup"><span data-stu-id="7468f-114">In this example, we will update the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log settings to set the rolling file size limit to 25000 KB (the default is 20000 KB).</span></span>  
  
1.  <span data-ttu-id="7468f-115">Démarrez Microsoft SQL Server Management Studio et connectez-vous à l'instance de SQL Server appropriée.</span><span class="sxs-lookup"><span data-stu-id="7468f-115">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="7468f-116">Dans l'Explorateur d'objets, cliquez avec le bouton droit sur le serveur, puis cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7468f-116">In Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7468f-117">Dans la fenêtre Éditeur de requête, copiez les instructions SQL suivantes :</span><span class="sxs-lookup"><span data-stu-id="7468f-117">In the Query Editor window, copy the following SQL statements:</span></span>  
  
    ```sql  
    -- Begin the transaction.  
    BEGIN TRAN  
    GO  
    -- set the XML value field for the row with name=ServerLogging  
    update DQS_MAIN.dbo.A_CONFIGURATION   
    set VALUE='<configuration>  
      <configSections>  
        <section name="loggingConfiguration" type="Microsoft.Practices.EnterpriseLibrary.Logging.Configuration.LoggingSettings, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" />  
      </configSections>  
      <loggingConfiguration name="Logging Application Block" tracingEnabled="true" defaultCategory="" logWarningsWhenNoCategoriesMatch="true">  
        <listeners>  
          <add fileName="###REPLACE_THIS_WITH_SQL_SERVER_INSTANCE_LOG_FOLDER_NAME###DQServerLog.###REPLACE_THIS_WITH_SQL_CATALOG_NAME###.log" footer="" formatter="Custom Text Formatter" header="" rollFileExistsBehavior="Increment" rollInterval="None" rollSizeKB="25000" timeStampPattern="yyyy-MM-dd" listenerDataType="Microsoft.Practices.EnterpriseLibrary.Logging.Configuration.RollingFlatFileTraceListenerData, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" traceOutputOptions="None" filter="All" type="Microsoft.Practices.EnterpriseLibrary.Logging.TraceListeners.RollingFlatFileTraceListener, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="Rolling Flat File Trace Listener" />  
        </listeners>  
        <formatters>  
          <add template="{timestamp(local)}|[{threadName}]|{dictionary({value}|)}{message}" type="Microsoft.Practices.EnterpriseLibrary.Logging.Formatters.TextFormatter, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="Custom Text Formatter" />  
        </formatters>  
        <logFilters>  
          <add enabled="true" type="Microsoft.Practices.EnterpriseLibrary.Logging.Filters.LogEnabledFilter, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="LogEnabled Filter" />  
        </logFilters>  
        <categorySources />  
        <specialSources>  
          <allEvents switchValue="All" name="All Events" />  
          <notProcessed switchValue="All" name="Unprocessed Category" />  
          <errors switchValue="All" name="Logging Errors & Warnings">  
            <listeners>  
              <add name="Rolling Flat File Trace Listener" />  
            </listeners>  
          </errors>  
        </specialSources>  
      </loggingConfiguration>  
    </configuration>'  
    WHERE NAME='ServerLogging'  
    GO  
    -- check the result  
    select * from DQS_MAIN.dbo.A_CONFIGURATION where NAME='ServerLogging'  
  
    -- Commit the transaction.  
    COMMIT TRAN  
  
    ```  
  
4.  <span data-ttu-id="7468f-118">Appuyez sur F5 pour exécuter les instructions.</span><span class="sxs-lookup"><span data-stu-id="7468f-118">Press F5 to execute the statements.</span></span> <span data-ttu-id="7468f-119">Vérifiez le volet **résultats** pour vérifier que les instructions ont été exécutées avec succès.</span><span class="sxs-lookup"><span data-stu-id="7468f-119">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
5.  <span data-ttu-id="7468f-120">Pour appliquer les modifications effectuées à la configuration de journalisation [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , vous devez exécuter les instructions Transact-SQL suivantes.</span><span class="sxs-lookup"><span data-stu-id="7468f-120">To apply changes done to the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging configuration, you must run the following Transact-SQL statements.</span></span> <span data-ttu-id="7468f-121">Ouvrez une nouvelle fenêtre de l'Éditeur de requête, puis collez les instructions Transact-SQL suivantes :</span><span class="sxs-lookup"><span data-stu-id="7468f-121">Open a new Query Editor window, and paste the following Transact-SQL statements:</span></span>  
  
    ```sql  
    USE [DQS_MAIN]  
    GO  
    DECLARE @return_value int  
    EXEC @return_value = [internal_core].[RefreshLogSettings]  
    SELECT 'Return Value' = @return_value  
    GO  
    ```  
  
6.  <span data-ttu-id="7468f-122">Appuyez sur F5 pour exécuter les instructions.</span><span class="sxs-lookup"><span data-stu-id="7468f-122">Press F5 to execute the statements.</span></span> <span data-ttu-id="7468f-123">Vérifiez le volet **résultats** pour vérifier que les instructions ont été exécutées avec succès.</span><span class="sxs-lookup"><span data-stu-id="7468f-123">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7468f-124">La configuration des paramètres de journalisation [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] est générée dynamiquement et stockée dans le fichier DQS_MAIN.Log, généralement disponible dans C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log si vous avez installé l'instance par défaut de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7468f-124">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging settings configuration is dynamically generated and stored in the DQS_MAIN.Log file, which is typically available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log if you installed the default instance of SQL Server.</span></span> <span data-ttu-id="7468f-125">Toutefois, les modifications apportées directement dans ce fichier ne se conservent pas et sont remplacées par les paramètres de configuration de la table A_CONFIGURATION de la base de données DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="7468f-125">However, changes done directly in this file do not hold, and are overwritten by the configuration settings in the A_CONFIGURATION table in the DQS_MAIN database.</span></span>  
  
##  <a name="configure-data-quality-client-log-settings"></a><a name="DQSClient"></a><span data-ttu-id="7468f-126">Configurer les paramètres du journal Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="7468f-126">Configure Data Quality Client Log Settings</span></span>  
 <span data-ttu-id="7468f-127">Le [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] fichier de configuration du paramètre de journal, DQLog.Client.xml, est généralement disponible dans C:\Program Files\Microsoft SQL Server\120\Tools\Binn\DQ\config. Le contenu du fichier XML est semblable au fichier XML que vous avez modifié précédemment pour les [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] paramètres de configuration du journal.</span><span class="sxs-lookup"><span data-stu-id="7468f-127">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log setting configuration file, DQLog.Client.xml, is typically available at C:\Program Files\Microsoft SQL Server\120\Tools\Binn\DQ\config. The contents of the XML file is similar to the XML file that you modified earlier for the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log configuration settings.</span></span> <span data-ttu-id="7468f-128">Pour configurer les paramètres des journaux [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="7468f-128">To configure the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log settings:</span></span>  
  
1.  <span data-ttu-id="7468f-129">Exécutez l'outil d'édition XML ou le Bloc-notes en tant qu'administrateur.</span><span class="sxs-lookup"><span data-stu-id="7468f-129">Run any XML editing tool or notepad as an administrator.</span></span>  
  
2.  <span data-ttu-id="7468f-130">Ouvrez le fichier DQLog.Client.xml dans l'outil ou le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="7468f-130">Open the DQLog.Client.xml file in the tool or notepad.</span></span>  
  
3.  <span data-ttu-id="7468f-131">Apportez les modifications requises et enregistrez le fichier pour appliquer les nouvelles modifications de journalisation.</span><span class="sxs-lookup"><span data-stu-id="7468f-131">Make the required changes, and save the file to apply the new logging changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7468f-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7468f-132">See Also</span></span>  
 [<span data-ttu-id="7468f-133">Configurer les niveaux de gravité pour les fichiers journaux DQS</span><span class="sxs-lookup"><span data-stu-id="7468f-133">Configure Severity Levels for DQS Log Files</span></span>](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)  
  
  
