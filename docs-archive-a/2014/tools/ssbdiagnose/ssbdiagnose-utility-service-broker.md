---
title: Utilitaire ssbdiagnose (Service Broker) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, runtime reports
- Service Broker, command prompt utilities
- troubleshooting [Service Broker], conversations
- troubleshooting [Service Broker], configurations
- command prompt utilities [Service Broker]
- Service Broker, troubleshooting
- Service Broker, configuration reports
- Service Broker, tools
- troubleshooting [Service Broker], runtime
- conversations [Service Broker], troubleshooting
- troubleshooting [Service Broker], ssbdiagnose utility
- tools [Service Broker], ssbdiagnose
- Service Broker, ssbdiagnose utility
- ssbdiagnose
ms.assetid: 0c1636e8-a3db-438e-be4c-1ea40d1f4877
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8efc581eebd7d8fa7fa265abb54168af78b57ca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704547"
---
# <a name="ssbdiagnose-utility-service-broker"></a><span data-ttu-id="69c01-102">Utilitaire ssbdiagnose (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="69c01-102">ssbdiagnose Utility (Service Broker)</span></span>
  <span data-ttu-id="69c01-103">L’utilitaire **ssbdiagnose** signale des problèmes rencontrés dans des conversations [!INCLUDE[ssSB](../../includes/sssb-md.md)] ou dans la configuration des services [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69c01-103">The **ssbdiagnose** utility reports issues in [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversations or the configuration of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services.</span></span> <span data-ttu-id="69c01-104">Des vérifications de configuration peuvent réalisées pour deux services ou pour un seul.</span><span class="sxs-lookup"><span data-stu-id="69c01-104">Configuration checks can be made for either two services or a single service.</span></span> <span data-ttu-id="69c01-105">Les problèmes sont signalés soit dans la fenêtre d’invite de commandes par un texte explicite, soit dans un fichier XML mis en forme qui peut être redirigé vers un fichier ou un autre programme.</span><span class="sxs-lookup"><span data-stu-id="69c01-105">Issues are reported either in the command prompt window as human-readable text, or as formatted XML that can be redirected to a file or another program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69c01-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="69c01-106">Syntax</span></span>  
  
```  
  
      ssbdiagnose   
[ [ -XML ]  
    [ -LEVEL { ERROR | WARNING | INFO } ]  
  [-IGNOREerror_id ] [ ...n]  
    [ <baseconnectionoptions> ]  
  { <configurationreport> | <runtimereport> }  
]  
| -?  
  
<configurationreport> ::=  
    CONFIGURATION  
  { [ FROM SERVICEservice_name  
      [ <fromconnectionoptions> ]  
      [ MIRROR <mirrorconnectionoptions> ]  
    ]  
    [ TO SERVICEservice_name[, broker_id ]  
      [ <toconnectionoptions> ]  
      [ MIRROR <mirrorconnectionoptions> ]  
    ]  
  }  
    ON CONTRACTcontract_name  
  [ ENCRYPTION { ON | OFF | ANONYMOUS } ]  
  
<runtime_report> ::=  
    RUNTIME  
    [-SHOWEVENTS ]  
        [ -NEW  
         [ -ID { conversation_handle  
                | conversation_group_id  
                 | conversation_id  
                  }  
        ] [ ...n]  
        ]  
    [ -TIMEOUTtimeout_interval ]  
    [ <runtimeconnectionoptions> ]  
  
<baseconnectionoptions> ::=  
  <connectionoptions>  
  
<fromconnectionoptions> ::=  
  <connectionoptions>  
  
<toconnectionoptions> ::=  
  <connectionoptions>  
  
<mirrorconnectionoptions> ::=  
  <connectionoptions>  
  
<runtimeconnectionoptions> ::=  
  [ CONNECT TO <connectionoptions> ] [ ...n]  
  
<connectionoptions> ::=  
    [ -E | { -Ulogin_id [ -Ppassword ] } ]  
  [ -Sserver_name[\instance_name] ]  
  [ -ddatabase_name ]  
  [ -llogin_timeout ]  
  
```  
  
## <a name="command-line-options"></a><span data-ttu-id="69c01-107">Options de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="69c01-107">Command Line Options</span></span>  
 <span data-ttu-id="69c01-108">**-XML**</span><span class="sxs-lookup"><span data-stu-id="69c01-108">**-XML**</span></span>  
 <span data-ttu-id="69c01-109">Spécifie que la sortie de **ssbdiagnose** doit être générée au format XML.</span><span class="sxs-lookup"><span data-stu-id="69c01-109">Specifies that the **ssbdiagnose** output be generated as formatted XML.</span></span> <span data-ttu-id="69c01-110">Ce fichier peut être redirigé vers un fichier ou une autre application.</span><span class="sxs-lookup"><span data-stu-id="69c01-110">This can be redirected to a file or to another application.</span></span> <span data-ttu-id="69c01-111">Si l’option **-XML** n’est pas spécifiée, la sortie de **ssbdiagnose** se présente sous forme de texte explicite.</span><span class="sxs-lookup"><span data-stu-id="69c01-111">If **-XML** is not specified, the **ssbdiagnose** output is formatted as human-readable text.</span></span>  
  
 <span data-ttu-id="69c01-112">**-LEVEL** { **ERROR** | **WARNING** | **INFO**}</span><span class="sxs-lookup"><span data-stu-id="69c01-112">**-LEVEL** { **ERROR** | **WARNING** | **INFO**}</span></span>  
 <span data-ttu-id="69c01-113">Spécifie le niveau des messages à signaler.</span><span class="sxs-lookup"><span data-stu-id="69c01-113">Specifies the level of messages to report.</span></span>  
  
 <span data-ttu-id="69c01-114">**ERROR**: signaler uniquement les messages d’erreur.</span><span class="sxs-lookup"><span data-stu-id="69c01-114">**ERROR**: report only error messages.</span></span>  
  
 <span data-ttu-id="69c01-115">**WARNING**: signaler les messages d’erreur et d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="69c01-115">**WARNING**: report error and warning messages.</span></span>  
  
 <span data-ttu-id="69c01-116">**INFO**: signaler les messages d’erreur, d’avertissement et d’information.</span><span class="sxs-lookup"><span data-stu-id="69c01-116">**INFO**: report error, warning, and informational messages.</span></span>  
  
 <span data-ttu-id="69c01-117">Le paramètre par défaut est **WARNING**.</span><span class="sxs-lookup"><span data-stu-id="69c01-117">The default setting is **WARNING**.</span></span>  
  
 <span data-ttu-id="69c01-118">**-IGNORE** *error_id*</span><span class="sxs-lookup"><span data-stu-id="69c01-118">**-IGNORE** *error_id*</span></span>  
 <span data-ttu-id="69c01-119">Spécifie que les erreurs ou les messages ayant l’ *ID_erreur* spécifié ne doivent pas être inclus dans les rapports.</span><span class="sxs-lookup"><span data-stu-id="69c01-119">Specifies that errors or messages that have the specified *error_id* not be included in reports.</span></span> <span data-ttu-id="69c01-120">Vous pouvez spécifier **-IGNORE** plusieurs fois pour supprimer plusieurs ID de message.</span><span class="sxs-lookup"><span data-stu-id="69c01-120">You can specify **-IGNORE** multiple times to suppress multiple message IDs.</span></span>  
  
 **\<baseconnectionoptions>**  
 <span data-ttu-id="69c01-121">Spécifie les informations de connexion de base utilisées par **ssbdiagnose** quand les options de connexion ne sont pas incluses dans une clause spécifique.</span><span class="sxs-lookup"><span data-stu-id="69c01-121">Specifies the base connection information that is used by **ssbdiagnose** when connection options are not included in a specific clause.</span></span> <span data-ttu-id="69c01-122">Les informations de connexion indiquées dans une clause spécifique remplacent celles figurant dans **baseconnectionoption** .</span><span class="sxs-lookup"><span data-stu-id="69c01-122">The connection information that is given in a specific clause overrides the **baseconnectionoption** information.</span></span> <span data-ttu-id="69c01-123">Ceci est effectué individuellement pour chaque paramètre.</span><span class="sxs-lookup"><span data-stu-id="69c01-123">This is performed separately for each parameter.</span></span> <span data-ttu-id="69c01-124">Par exemple, si les options **-S** et **-d** sont spécifiées dans **baseconnetionoptions**, et si seule l’option **-d** est spécifiée dans **oconnetionoptions**, **ssbdiagnose** utilise -S de **baseconnetionoptions** et -d de **toconnetionoptions**.</span><span class="sxs-lookup"><span data-stu-id="69c01-124">For example, if both **-S** and **-d** are specified in **baseconnetionoptions**, and only **-d** is specified in **toconnetionoptions**, **ssbdiagnose** uses -S from **baseconnetionoptions** and -d from **toconnetionoptions**.</span></span>  
  
 <span data-ttu-id="69c01-125">**CONFIGURATION**</span><span class="sxs-lookup"><span data-stu-id="69c01-125">**CONFIGURATION**</span></span>  
 <span data-ttu-id="69c01-126">Demande un rapport des erreurs de configuration entre une paire de services [!INCLUDE[ssSB](../../includes/sssb-md.md)] ou pour un service unique.</span><span class="sxs-lookup"><span data-stu-id="69c01-126">Requests a report of configuration errors between a pair of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services, or for a single service.</span></span>  
  
 <span data-ttu-id="69c01-127">**FROM SERVICE** *service_name*</span><span class="sxs-lookup"><span data-stu-id="69c01-127">**FROM SERVICE** *service_name*</span></span>  
 <span data-ttu-id="69c01-128">Spécifie le service qui lance les conversations.</span><span class="sxs-lookup"><span data-stu-id="69c01-128">Specifies the service that initiates conversations.</span></span>  
  
 **\<fromconnectionoptions>**  
 <span data-ttu-id="69c01-129">Spécifie les informations requises pour se connecter à la base de données contenant le service initiateur.</span><span class="sxs-lookup"><span data-stu-id="69c01-129">Specifies the information that is required to connect to the database that holds the initiator service.</span></span> <span data-ttu-id="69c01-130">Si **fromconnectionoptions** n’est pas spécifié, **ssbdiagnose** utilise les informations de connexion de **baseconnectionoptions** pour se connecter à la base de données de l’initiateur.</span><span class="sxs-lookup"><span data-stu-id="69c01-130">If **fromconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the initiator database.</span></span> <span data-ttu-id="69c01-131">Si **fromconnectionoptions** est spécifié, la base de données contenant le service initiateur doit y être indiquée.</span><span class="sxs-lookup"><span data-stu-id="69c01-131">If **fromconnectionoptions** is specified it must include the database that contains the initiator service.</span></span> <span data-ttu-id="69c01-132">Si **fromconnectionoptions** n’est pas spécifié, **baseconnectionoptions** doit spécifier la base de données de l’initiateur.</span><span class="sxs-lookup"><span data-stu-id="69c01-132">If **fromconnectionoptions** is not specified, the **baseconnectionoptions** must specify the initiator database.</span></span>  
  
 <span data-ttu-id="69c01-133">**TO SERVICE** *service_name*[, *broker_id* ]</span><span class="sxs-lookup"><span data-stu-id="69c01-133">**TO SERVICE** *service_name*[, *broker_id* ]</span></span>  
 <span data-ttu-id="69c01-134">Spécifie le service qui est la cible des conversations.</span><span class="sxs-lookup"><span data-stu-id="69c01-134">Specifies the service that is the target for the conversations.</span></span>  
  
 <span data-ttu-id="69c01-135">*nom_service*: spécifie le nom du service cible.</span><span class="sxs-lookup"><span data-stu-id="69c01-135">*service_name*: specifies the name of the target service.</span></span>  
  
 <span data-ttu-id="69c01-136">*ID_broker*: spécifie l’ID [!INCLUDE[ssSB](../../includes/sssb-md.md)] qui identifie la base de données cible.</span><span class="sxs-lookup"><span data-stu-id="69c01-136">*broker_id*: specifies the [!INCLUDE[ssSB](../../includes/sssb-md.md)] ID that identifies the target database.</span></span> <span data-ttu-id="69c01-137">*ID_broker* est un GUID.</span><span class="sxs-lookup"><span data-stu-id="69c01-137">*broker_id* is a GUID.</span></span> <span data-ttu-id="69c01-138">Vous pouvez exécuter la requête suivante dans la base de données cible pour le rechercher :</span><span class="sxs-lookup"><span data-stu-id="69c01-138">You can run the following query in the target database to find it:</span></span>  
  
```  
SELECT service_broker_guid  
FROM sys.databases  
WHERE database_id = DB_ID();  
```  
  
 **\<toconnectionoptions>**  
 <span data-ttu-id="69c01-139">Spécifie les informations requises pour connecter la base de données contenant le service cible.</span><span class="sxs-lookup"><span data-stu-id="69c01-139">Specifies the information that is required to connect the database that holds the target service.</span></span> <span data-ttu-id="69c01-140">Si **toconnectionoptions** n’est pas spécifié, **ssbdiagnose** utilise les informations de connexion de **baseconnectionoptions** pour se connecter à la base de données cible.</span><span class="sxs-lookup"><span data-stu-id="69c01-140">If **toconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the target database.</span></span>  
  
 <span data-ttu-id="69c01-141">**MIRROR**</span><span class="sxs-lookup"><span data-stu-id="69c01-141">**MIRROR**</span></span>  
 <span data-ttu-id="69c01-142">Spécifie que le service [!INCLUDE[ssSB](../../includes/sssb-md.md)] associé est hébergé par une base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="69c01-142">Specifies that the associated [!INCLUDE[ssSB](../../includes/sssb-md.md)] service is hosted in a mirrored database.</span></span> <span data-ttu-id="69c01-143">**ssbdiagnose** vérifie si l’itinéraire du service est un itinéraire mis en miroir, où la clause MIRROR_ADDRESS est spécifiée sur CREATE ROUTE.</span><span class="sxs-lookup"><span data-stu-id="69c01-143">**ssbdiagnose** verifies that the route to the service is a mirrored route, where MIRROR_ADDRESS was specified on CREATE ROUTE.</span></span>  
  
 **\<mirrorconnectionoptions>**  
 <span data-ttu-id="69c01-144">Spécifie les informations requises pour se connecter à la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="69c01-144">Specifies the information that is required to connect to the mirror database.</span></span> <span data-ttu-id="69c01-145">Si **mirrorconnectionoptions** n’est pas spécifié, **ssbdiagnose** utilise les informations de connexion de **baseconnectionoptions** pour se connecter à la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="69c01-145">If **mirrorconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the mirror database.</span></span>  
  
 <span data-ttu-id="69c01-146">**ON CONTRACT** *contract_name*</span><span class="sxs-lookup"><span data-stu-id="69c01-146">**ON CONTRACT** *contract_name*</span></span>  
 <span data-ttu-id="69c01-147">Demande que **ssbdiagnose** vérifie uniquement les configurations qui utilisent le contrat spécifié.</span><span class="sxs-lookup"><span data-stu-id="69c01-147">Requests that **ssbdiagnose** only check configurations that use the specified contract.</span></span> <span data-ttu-id="69c01-148">Si ON CONTRACT n’est pas spécifié, **ssbdiagnose** effectue un rapport sur le contrat nommé DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="69c01-148">If ON CONTRACT is not specified, **ssbdiagnose** reports on the contract named DEFAULT.</span></span>  
  
 <span data-ttu-id="69c01-149">**ENCRYPTION** { **ON** | **OFF** | **ANONYMOUS** }</span><span class="sxs-lookup"><span data-stu-id="69c01-149">**ENCRYPTION** { **ON** | **OFF** | **ANONYMOUS** }</span></span>  
 <span data-ttu-id="69c01-150">Demande que la configuration du dialogue soit vérifiée pour le niveau de chiffrement spécifié :</span><span class="sxs-lookup"><span data-stu-id="69c01-150">Requests verification that the dialog is correctly configured for the specified level of encryption:</span></span>  
  
 <span data-ttu-id="69c01-151">**ON** : Paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="69c01-151">**ON**: Default setting.</span></span> <span data-ttu-id="69c01-152">La sécurité de dialogue complète est configurée.</span><span class="sxs-lookup"><span data-stu-id="69c01-152">Full dialog security is configured.</span></span> <span data-ttu-id="69c01-153">Des certificats ont été déployés des deux côtés du dialogue, une liaison de service distant est présente et l'instruction GRANT SEND du service cible a spécifié l'utilisateur initiateur.</span><span class="sxs-lookup"><span data-stu-id="69c01-153">Certificates have been deployed on both sides of the dialog, a remote service binding is present, and the GRANT SEND statement for the target service specified the initiator user.</span></span>  
  
 <span data-ttu-id="69c01-154">**OFF** : Aucune sécurité de dialogue n'est configurée.</span><span class="sxs-lookup"><span data-stu-id="69c01-154">**OFF**: No dialog security is configured.</span></span> <span data-ttu-id="69c01-155">Aucun certificat n’a été déployé, aucune liaison de service distant n’a été créée, et l’instruction GRANT SEND du service initiateur a spécifié le rôle **public** .</span><span class="sxs-lookup"><span data-stu-id="69c01-155">No certificates have been deployed, no remote service binding was created, and the GRANT SEND for the initiator service specified the **public** role.</span></span>  
  
 <span data-ttu-id="69c01-156">**ANONYMOUS** : La sécurité de dialogue anonyme est configurée.</span><span class="sxs-lookup"><span data-stu-id="69c01-156">**ANONYMOUS**: Anonymous dialog security is configured.</span></span> <span data-ttu-id="69c01-157">Un certificat a été déployé, la liaison de service distant a spécifié la clause ANONYMOUS, et l’instruction GRANT SEND du service cible a spécifié le rôle **public** .</span><span class="sxs-lookup"><span data-stu-id="69c01-157">One certificate has been deployed, the remote service binding specified the anonymous clause, and the GRANT SEND for the target service specified the **public** role.</span></span>  
  
 <span data-ttu-id="69c01-158">**RUNTIME**</span><span class="sxs-lookup"><span data-stu-id="69c01-158">**RUNTIME**</span></span>  
 <span data-ttu-id="69c01-159">Demande un rapport sur les problèmes à l'origine d'erreurs d'exécution pour une conversation [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69c01-159">Requests a report of issues that cause runtime errors for a [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversation.</span></span> <span data-ttu-id="69c01-160">Si ni **-NEW** ni **-ID** n’est spécifiée, **ssbdiagnose** surveille toutes les conversations dans toutes les bases de données spécifiées dans les options de connexion.</span><span class="sxs-lookup"><span data-stu-id="69c01-160">If neither **-NEW** or **-ID** are specified, **ssbdiagnose** monitors all conversations in all databases specified in the connection options.</span></span> <span data-ttu-id="69c01-161">Si l’option **-NEW** ou **-ID** est spécifiée, **ssbdiagnose** génère la liste des ID spécifiés dans les paramètres.</span><span class="sxs-lookup"><span data-stu-id="69c01-161">If **-NEW** or **-ID** are specified, **ssbdiagnose** builds a list of the IDs specified in the parameters.</span></span>  
  
 <span data-ttu-id="69c01-162">Pendant son exécution, **ssbdiagnose** enregistre tous les événements [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] qui indiquent des erreurs d’exécution.</span><span class="sxs-lookup"><span data-stu-id="69c01-162">While **ssbdiagnose** is running, it records all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events that indicate runtime errors.</span></span> <span data-ttu-id="69c01-163">Il enregistre les événements qui se produisent pour les ID spécifiés, ainsi que les événements au niveau système.</span><span class="sxs-lookup"><span data-stu-id="69c01-163">It records the events that occur for the specified IDs, plus system-level events.</span></span> <span data-ttu-id="69c01-164">Si des erreurs d’exécution sont rencontrées, **ssbdiagnose** exécute un rapport de configuration sur la configuration associée.</span><span class="sxs-lookup"><span data-stu-id="69c01-164">If runtime errors are encountered, **ssbdiagnose** runs a configuration report on the associated configuration.</span></span>  
  
 <span data-ttu-id="69c01-165">Par défaut, les erreurs d'exécution ne sont pas incluses dans le rapport de sortie, seuls les résultats de l'analyse de la configuration le sont.</span><span class="sxs-lookup"><span data-stu-id="69c01-165">By default, runtime errors are not included in the output report, only the results of the configuration analysis.</span></span> <span data-ttu-id="69c01-166">Utilisez **-SHOWEVENTS** pour inclure les erreurs d’exécution dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="69c01-166">Use **-SHOWEVENTS** to have the runtime errors included in the report.</span></span>  
  
 <span data-ttu-id="69c01-167">**-SHOWEVENTS**</span><span class="sxs-lookup"><span data-stu-id="69c01-167">**-SHOWEVENTS**</span></span>  
 <span data-ttu-id="69c01-168">Spécifie que **ssbdiagnose** doit signaler les événements [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] dans le cadre d’un rapport RUNTIME.</span><span class="sxs-lookup"><span data-stu-id="69c01-168">Specifies that **ssbdiagnose** report [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events during a RUNTIME report.</span></span> <span data-ttu-id="69c01-169">Seuls les événements considérés comme des conditions d'erreur sont signalés.</span><span class="sxs-lookup"><span data-stu-id="69c01-169">Only events that are considered error conditions are reported.</span></span> <span data-ttu-id="69c01-170">Par défaut, **ssbdiagnose** ne fait que surveiller les événements d’erreurs. Il ne les signale pas dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="69c01-170">By default, **ssbdiagnose** only monitors error events; it does not report them in the output.</span></span>  
  
 <span data-ttu-id="69c01-171">**-NEW**</span><span class="sxs-lookup"><span data-stu-id="69c01-171">**-NEW**</span></span>  
 <span data-ttu-id="69c01-172">Demande le contrôle d’exécution de la première conversation qui commence après le démarrage de **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="69c01-172">Requests runtime monitoring of the first conversation that begins after **ssbdiagnose** starts running.</span></span>  
  
 <span data-ttu-id="69c01-173">**-ID**</span><span class="sxs-lookup"><span data-stu-id="69c01-173">**-ID**</span></span>  
 <span data-ttu-id="69c01-174">Demande que les éléments de conversation spécifiés fassent l'objet d'une surveillance au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="69c01-174">Requests runtime monitoring of the specified conversation elements.</span></span> <span data-ttu-id="69c01-175">Vous pouvez spécifier **-ID** plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="69c01-175">You can specify **-ID** multiple times.</span></span>  
  
 <span data-ttu-id="69c01-176">Si vous spécifiez un descripteur de conversation, seuls les événements associés au point de terminaison de conversation associé sont signalés.</span><span class="sxs-lookup"><span data-stu-id="69c01-176">If you specify a conversation handle, only events associated with the associated conversation endpoint are reported.</span></span> <span data-ttu-id="69c01-177">Si vous spécifiez un ID de conversation, tous les événements de cette conversation et de ses points de terminaison initiateur et cible sont signalés.</span><span class="sxs-lookup"><span data-stu-id="69c01-177">If you specify a conversation ID, all events for that conversation and its initiator and target endpoints are reported.</span></span> <span data-ttu-id="69c01-178">Si un ID de groupe de conversations est spécifié, tous les événements de toutes les conversations et de tous les points de terminaison du groupe de conversations sont signalés.</span><span class="sxs-lookup"><span data-stu-id="69c01-178">If a conversation group ID is specified, all events for all conversations and endpoints in the conversation group are reported.</span></span>  
  
 <span data-ttu-id="69c01-179">*conversation_handle*</span><span class="sxs-lookup"><span data-stu-id="69c01-179">*conversation_handle*</span></span>  
 <span data-ttu-id="69c01-180">Identificateur unique qui identifie un point de terminaison de conversation dans une application.</span><span class="sxs-lookup"><span data-stu-id="69c01-180">A unique identifier that identifies a conversation endpoint in an application.</span></span> <span data-ttu-id="69c01-181">Les descripteurs de conversation sont uniques à un point de terminaison d'une conversation, les points de terminaison initiateur et cible ont des descripteurs de conversation distincts.</span><span class="sxs-lookup"><span data-stu-id="69c01-181">Conversation handles are unique to one endpoint of a conversation, the initiator and target endpoints have separate conversation handles.</span></span>  
  
 <span data-ttu-id="69c01-182">Les descripteurs de conversation sont retournés aux applications par le *@dialog_handle* paramètre de l’instruction **Begin Dialog** , et la `conversation_handle` colonne dans le jeu de résultats d’une instruction **Receive** .</span><span class="sxs-lookup"><span data-stu-id="69c01-182">Conversation handles are returned to applications by the *@dialog_handle* parameter of the **BEGIN DIALOG** statement, and the `conversation_handle` column in the result set of a **RECEIVE** statement.</span></span>  
  
 <span data-ttu-id="69c01-183">Les descripteurs de conversation sont signalés dans la `conversation_handle` colonne des affichages catalogue **sys. transmission_queue** et **sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="69c01-183">Conversation handles are reported in the `conversation_handle` column of the **sys.transmission_queue** and **sys.conversation_endpoints** catalog views.</span></span>  
  
 <span data-ttu-id="69c01-184">*conversation_group_id*</span><span class="sxs-lookup"><span data-stu-id="69c01-184">*conversation_group_id*</span></span>  
 <span data-ttu-id="69c01-185">Identificateur unique qui identifie un groupe de conversations.</span><span class="sxs-lookup"><span data-stu-id="69c01-185">The unique identifier that identifies a conversation group.</span></span>  
  
 <span data-ttu-id="69c01-186">Les ID de groupe de conversations sont retournés aux applications par le *@conversation_group_id* paramètre de l’instruction d' **extraction de groupe de conversations** et de la `conversation_group_id` colonne dans le jeu de résultats d’une instruction **Receive** .</span><span class="sxs-lookup"><span data-stu-id="69c01-186">Conversation group IDs are returned to applications by the *@conversation_group_id* parameter of the **GET CONVERSATION GROUP** statement and the `conversation_group_id` column in the result set of a **RECEIVE** statement.</span></span>  
  
 <span data-ttu-id="69c01-187">Les ID de groupe de conversations sont signalés dans les `conversation_group_id` colonnes des affichages catalogue **sys. conversation_groups** et **sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="69c01-187">Conversation group IDs are reported in the `conversation_group_id` columns of the **sys.conversation_groups** and **sys.conversation_endpoints** catalog views.</span></span>  
  
 <span data-ttu-id="69c01-188">*conversation_id*</span><span class="sxs-lookup"><span data-stu-id="69c01-188">*conversation_id*</span></span>  
 <span data-ttu-id="69c01-189">Identificateur unique qui identifie une conversation.</span><span class="sxs-lookup"><span data-stu-id="69c01-189">The unique identifier that identifies a conversation.</span></span> <span data-ttu-id="69c01-190">Les ID de conversation sont les mêmes pour les points de terminaison initiateur et cible d'une conversation.</span><span class="sxs-lookup"><span data-stu-id="69c01-190">Conversation IDs are the same for both the initiator and target endpoints of a conversation.</span></span>  
  
 <span data-ttu-id="69c01-191">Les ID de conversation sont signalés dans la `conversation_id` colonne de l’affichage catalogue **sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="69c01-191">Conversation IDs are reported in the `conversation_id` column of the **sys.conversation_endpoints** catalog view.</span></span>  
  
 <span data-ttu-id="69c01-192">**-TIMEOUT** *timeout_interval*</span><span class="sxs-lookup"><span data-stu-id="69c01-192">**-TIMEOUT** *timeout_interval*</span></span>  
 <span data-ttu-id="69c01-193">Spécifie la durée d’exécution du rapport **RUNTIME** en secondes.</span><span class="sxs-lookup"><span data-stu-id="69c01-193">Specifies the number of seconds for a **RUNTIME** report to run.</span></span> <span data-ttu-id="69c01-194">Si vous ne spécifiez pas **-TIMEOUT** , le rapport d’exécution s’exécute indéfiniment.</span><span class="sxs-lookup"><span data-stu-id="69c01-194">If **-TIMEOUT** is not specified the runtime report runs indefinitely.</span></span> <span data-ttu-id="69c01-195">**-TIMEOUT** est utilisé uniquement sur les rapports **RUNTIME** , et non sur les rapports **CONFIGURATION** .</span><span class="sxs-lookup"><span data-stu-id="69c01-195">**-TIMEOUT** is used only on **RUNTIME** reports, not **CONFIGURATION** reports.</span></span> <span data-ttu-id="69c01-196">Utilisez Ctrl+C pour quitter **ssbdiagnose** si **-TIMEOUT** n’a pas été spécifié, ou pour terminer un rapport d’exécution avant **-** l’expiration du délai d’attente.</span><span class="sxs-lookup"><span data-stu-id="69c01-196">Use ctrl + C to quit **ssbdiagnose** if **-TIMEOUT** was not specified or to end a runtime report before the time**-** out interval expires.</span></span> <span data-ttu-id="69c01-197">*intervalle_délai_d’attente* doit être un nombre compris entre 1 et 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="69c01-197">*timeout_interval* must be a number between 1 and 2,147,483,647.</span></span>  
  
 **\<runtimeconnectionoptions>**  
 <span data-ttu-id="69c01-198">Spécifie les informations de connexion pour les bases de données contenant les services associés aux éléments de conversation qui sont surveillés.</span><span class="sxs-lookup"><span data-stu-id="69c01-198">Specifies the connection information for the databases that contain the services associated with conversation elements being monitored.</span></span> <span data-ttu-id="69c01-199">Si tous les services se trouvent dans la même base de données, vous ne devez spécifier qu’une seule clause **CONNECT TO** .</span><span class="sxs-lookup"><span data-stu-id="69c01-199">If all the services are in the same database, you only have to specify one **CONNECT TO** clause.</span></span> <span data-ttu-id="69c01-200">Si les services se trouvent dans des bases de données séparées, vous devez fournir une clause **CONNECT TO** pour chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="69c01-200">If the services are in separate databases you must supply a **CONNECT TO** clause for each database.</span></span> <span data-ttu-id="69c01-201">Si **runtimeconnectionoptions** n’est pas spécifié, **ssbdiagnose** utilise les informations de connexion de **baseconnectionoptions**.</span><span class="sxs-lookup"><span data-stu-id="69c01-201">If **runtimeconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions**.</span></span>  
  
 <span data-ttu-id="69c01-202">**-E**</span><span class="sxs-lookup"><span data-stu-id="69c01-202">**-E**</span></span>  
 <span data-ttu-id="69c01-203">Ouvrir une connexion par le biais de l’authentification Windows à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] en utilisant votre compte Windows actuel comme ID de connexion.</span><span class="sxs-lookup"><span data-stu-id="69c01-203">Open a Windows Authentication connection to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by using your current Windows account as the login ID.</span></span> <span data-ttu-id="69c01-204">La connexion doit être membre du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="69c01-204">The login must be a member of the **sysadmin** fixed-server role.</span></span>  
  
 <span data-ttu-id="69c01-205">L'option -E ignore les paramètres d'utilisateur et de mot de passe des variables d'environnement SQLCMDUSER et SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="69c01-205">The -E option ignores the user and password settings of the SQLCMDUSER and SQLCMDPASSWORD environment variables.</span></span>  
  
 <span data-ttu-id="69c01-206">Si ni l’option **-E** ni l’option **-U** n’est spécifiée, **ssbdiagnose** utilise la valeur de la variable d’environnement SQLCMDUSER.</span><span class="sxs-lookup"><span data-stu-id="69c01-206">If neither **-E** nor **-U** is specified, **ssbdiagnose** uses the value from the SQLCMDUSER environment variable.</span></span> <span data-ttu-id="69c01-207">Si cette variable n’est pas définie non plus, **ssbdiagnose** utilise l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="69c01-207">If SQLCMDUSER is not set either, **ssbdiagnose** uses Windows Authentication.</span></span>  
  
 <span data-ttu-id="69c01-208">Si l’option **-E** est utilisée avec l’option **-U** ou **-P** , un message d’erreur est généré.</span><span class="sxs-lookup"><span data-stu-id="69c01-208">If the **-E** option is used together with the **-U** option or the **-P** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="69c01-209">**-U** *login_id*</span><span class="sxs-lookup"><span data-stu-id="69c01-209">**-U** *login_id*</span></span>  
 <span data-ttu-id="69c01-210">Ouvrir une connexion par le biais de l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant l’ID de connexion spécifié.</span><span class="sxs-lookup"><span data-stu-id="69c01-210">Open a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication connection by using the specified login ID.</span></span> <span data-ttu-id="69c01-211">La connexion doit être membre du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="69c01-211">The login must be a member of the **sysadmin** fixed-server role.</span></span>  
  
 <span data-ttu-id="69c01-212">Si ni l’option **-E** ni l’option **-U** n’est spécifiée, **ssbdiagnose** utilise la valeur de la variable d’environnement SQLCMDUSER.</span><span class="sxs-lookup"><span data-stu-id="69c01-212">If neither **-E** nor **-U** is specified, **ssbdiagnose** uses the value from the SQLCMDUSER environment variable.</span></span> <span data-ttu-id="69c01-213">Si cette variable n’est pas définie non plus, **ssbdiagnose** essaie de se connecter en utilisant le mode d’authentification Windows sur la base du compte Windows de l’utilisateur qui exécute **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="69c01-213">If SQLCMDUSER is not set either, **ssbdiagnose** tries to connect by using Windows Authentication mode based on the Windows account of the user who is running **ssbdiagnose**.</span></span>  
  
 <span data-ttu-id="69c01-214">Si l’option **-U** est utilisée avec l’option **-E** , un message d’erreur est généré.</span><span class="sxs-lookup"><span data-stu-id="69c01-214">If the **-U** option is used together with the **-E** option, an error message is generated.</span></span> <span data-ttu-id="69c01-215">Si l’option **-U** est suivie de plusieurs arguments, un message d’erreur est généré et le programme se termine.</span><span class="sxs-lookup"><span data-stu-id="69c01-215">If the **-U** option is followed by more than one argument, an error message is generated and the program exits.</span></span>  
  
 <span data-ttu-id="69c01-216">**-P** *password*</span><span class="sxs-lookup"><span data-stu-id="69c01-216">**-P** *password*</span></span>  
 <span data-ttu-id="69c01-217">Spécifie le mot de passe de l’ID de connexion **-U** .</span><span class="sxs-lookup"><span data-stu-id="69c01-217">Specifies the password for the **-U** login ID.</span></span> <span data-ttu-id="69c01-218">Les mots de passe respectent la casse.</span><span class="sxs-lookup"><span data-stu-id="69c01-218">Passwords are case sensitive.</span></span> <span data-ttu-id="69c01-219">Si vous utilisez l’option **-U** mais pas l’option **-P** , **ssbdiagnose** utilise la valeur de la variable d’environnement SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="69c01-219">If the **-U** option is used and the **-P** option is not used, **ssbdiagnose** uses the value from the SQLCMDPASSWORD environment variable.</span></span> <span data-ttu-id="69c01-220">Si cette variable n’est pas définie non plus, **ssbdiagnose** invite l’utilisateur à entrer un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="69c01-220">If SQLCMDPASSWORD is not set either, **ssbdiagnose** prompts the user for a password.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="69c01-221">Lorsque vous tapez une commande SET SQLCMDPASSWORD, votre mot de passe est visible par quiconque regarde votre moniteur.</span><span class="sxs-lookup"><span data-stu-id="69c01-221">When you type a SET SQLCMDPASSWORD command, your password will be visible to anyone who can see your monitor.</span></span>  
  
 <span data-ttu-id="69c01-222">Si l’option **-P** est spécifiée sans mot de passe, **ssbdiagnose** utilise le mot de passe par défaut (NULL).</span><span class="sxs-lookup"><span data-stu-id="69c01-222">If the **-P** option is specified without a password **ssbdiagnose** uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteStrongPass](../../includes/ssnotestrongpass-md.md)]<span data-ttu-id="69c01-223">Pour plus d’informations, consultez [Mots de passe forts](../../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="69c01-223">For more information, see [Strong Passwords](../../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="69c01-224">L’invite de mot de passe s’affiche en imprimant l’invite de commande sur la console, comme suit : `Password:`</span><span class="sxs-lookup"><span data-stu-id="69c01-224">The password prompt is displayed by printing the password prompt to the console, as follows: `Password:`</span></span>  
  
 <span data-ttu-id="69c01-225">L'entrée de l'utilisateur est masquée,</span><span class="sxs-lookup"><span data-stu-id="69c01-225">User input is hidden.</span></span> <span data-ttu-id="69c01-226">ce qui signifie que rien ne s'affiche et que le curseur reste immobile.</span><span class="sxs-lookup"><span data-stu-id="69c01-226">This means that nothing is displayed and the cursor stays in position.</span></span>  
  
 <span data-ttu-id="69c01-227">Si l’option **-P** est utilisée avec l’option **-E** , un message d’erreur est généré.</span><span class="sxs-lookup"><span data-stu-id="69c01-227">If the **-P** option is used with the **-E** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="69c01-228">Si l’option **-P** est suivie de plusieurs arguments, un message d’erreur est généré.</span><span class="sxs-lookup"><span data-stu-id="69c01-228">If the **-P** option is followed by more than one argument, an error message is generated.</span></span>  
  
 <span data-ttu-id="69c01-229">**-S** *server_name*[\\*instance_name*]</span><span class="sxs-lookup"><span data-stu-id="69c01-229">**-S** *server_name*[\\*instance_name*]</span></span>  
 <span data-ttu-id="69c01-230">Spécifie l’instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] qui contient les services [!INCLUDE[ssSB](../../includes/sssb-md.md)] à analyser.</span><span class="sxs-lookup"><span data-stu-id="69c01-230">Specifies the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that holds the [!INCLUDE[ssSB](../../includes/sssb-md.md)] services to be analyzed.</span></span>  
  
 <span data-ttu-id="69c01-231">Spécifiez *nom_serveur* pour vous connecter à l’instance par défaut du [!INCLUDE[ssDE](../../includes/ssde-md.md)] sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="69c01-231">Specify *server_name* to connect to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="69c01-232">Spécifiez *server_name ***\\*** instance_name* pour vous connecter à une instance nommée du [!INCLUDE[ssDE](../../includes/ssde-md.md)] sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="69c01-232">Specify *server_name***\\***instance_name* to connect to a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="69c01-233">Si vous ne spécifiez pas l’option **-S** , **ssbdiagnose** utilise la valeur de la variable d’environnement SQLCMDSERVER.</span><span class="sxs-lookup"><span data-stu-id="69c01-233">If **-S** is not specified, **ssbdiagnose** uses the value of the SQLCMDSERVER environment variable.</span></span> <span data-ttu-id="69c01-234">Si cette variable n’est pas définie non plus, **ssbdiagnose** se connecte à l’instance par défaut du [!INCLUDE[ssDE](../../includes/ssde-md.md)] sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="69c01-234">If SQLCMDSERVER is not set either, **ssbdiagnose** connects to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="69c01-235">**-d** *database_name*</span><span class="sxs-lookup"><span data-stu-id="69c01-235">**-d** *database_name*</span></span>  
 <span data-ttu-id="69c01-236">Spécifie la base de données qui contient les services [!INCLUDE[ssSB](../../includes/sssb-md.md)] à analyser.</span><span class="sxs-lookup"><span data-stu-id="69c01-236">Specifies the database that holds the [!INCLUDE[ssSB](../../includes/sssb-md.md)] services to be analyzed.</span></span> <span data-ttu-id="69c01-237">Si cette base de données n'existe pas, un message d'erreur est généré.</span><span class="sxs-lookup"><span data-stu-id="69c01-237">If the database does not exist, an error message is generated.</span></span> <span data-ttu-id="69c01-238">Si vous ne spécifiez pas l’option **-d** , la valeur par défaut est la base de données spécifiée dans la propriété de base de données par défaut de votre connexion.</span><span class="sxs-lookup"><span data-stu-id="69c01-238">If **-d** is not specified, the default is the database specified in the default-database property for your login.</span></span>  
  
 <span data-ttu-id="69c01-239">**-l** *login_timeout*</span><span class="sxs-lookup"><span data-stu-id="69c01-239">**-l** *login_timeout*</span></span>  
 <span data-ttu-id="69c01-240">Spécifie le délai d'attente d'une tentative de connexion à un serveur (en secondes). Si vous ne spécifiez pas l’option **-l** , **ssbdiagnose** utilise la valeur définie pour la variable d’environnement SQLCMDLOGINTIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="69c01-240">Specifies the number of seconds before an attempt to connect to a server times out. If **-l** is not specified, **ssbdiagnose** uses the value set for the SQLCMDLOGINTIMEOUT environment variable.</span></span> <span data-ttu-id="69c01-241">Si cette variable n'est pas définie non plus, le délai d'attente par défaut est de trente secondes.</span><span class="sxs-lookup"><span data-stu-id="69c01-241">If SQLCMDLOGINTIMEOUT is not set either, the default time-out is thirty seconds.</span></span> <span data-ttu-id="69c01-242">Le délai d'attente de la connexion doit être un nombre compris entre 0 et 65534.</span><span class="sxs-lookup"><span data-stu-id="69c01-242">The login time-out must be a number between 0 and 65534.</span></span> <span data-ttu-id="69c01-243">Si la valeur fournie n’est pas numérique ou n’est pas comprise dans cet intervalle, **ssbdiagnose** génère un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="69c01-243">If the value that is supplied is not numeric or does not fall into that range, **ssbdiagnose** generates an error message.</span></span> <span data-ttu-id="69c01-244">Une valeur de 0 spécifie un délai d'attente infini.</span><span class="sxs-lookup"><span data-stu-id="69c01-244">A value of 0 specifies time-out to be infinite.</span></span>  
  
 <span data-ttu-id="69c01-245">**-?**</span><span class="sxs-lookup"><span data-stu-id="69c01-245">**-?**</span></span>  
 <span data-ttu-id="69c01-246">Affiche l'aide de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="69c01-246">Displays command line help.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69c01-247">Notes</span><span class="sxs-lookup"><span data-stu-id="69c01-247">Remarks</span></span>  
 <span data-ttu-id="69c01-248">Utilisez **ssbdiagnose** pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="69c01-248">Use **ssbdiagnose** to do the following:</span></span>  
  
-   <span data-ttu-id="69c01-249">Confirmer qu'une application [!INCLUDE[ssSB](../../includes/sssb-md.md)] récemment configurée ne contient pas d'erreurs de configuration.</span><span class="sxs-lookup"><span data-stu-id="69c01-249">Confirm that there are no configuration errors in a newly configured [!INCLUDE[ssSB](../../includes/sssb-md.md)] application.</span></span>  
  
-   <span data-ttu-id="69c01-250">Confirmer l'absence d'erreurs de configuration après modification de la configuration d'une application [!INCLUDE[ssSB](../../includes/sssb-md.md)] existante.</span><span class="sxs-lookup"><span data-stu-id="69c01-250">Confirm that there are no configuration errors after changing the configuration of an existing [!INCLUDE[ssSB](../../includes/sssb-md.md)] application.</span></span>  
  
-   <span data-ttu-id="69c01-251">Confirmer l'absence d'erreurs de configuration après qu'une base de données [!INCLUDE[ssSB](../../includes/sssb-md.md)] a été détachée puis rattachée à une nouvelle instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69c01-251">Confirm that there are no configuration errors after a [!INCLUDE[ssSB](../../includes/sssb-md.md)] database is detached and then reattached to a new instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="69c01-252">Rechercher d'éventuelles erreurs de configuration lorsque des messages ne sont pas transmis avec succès entre des services.</span><span class="sxs-lookup"><span data-stu-id="69c01-252">Research whether there are configuration errors when messages are not successfully transmitted between services.</span></span>  
  
-   <span data-ttu-id="69c01-253">Obtenir un rapport sur toute erreur se produisant dans un jeu d'éléments de conversation [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69c01-253">Get a report of any errors that occur in a set of [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversation elements.</span></span>  
  
## <a name="configuration-reporting"></a><span data-ttu-id="69c01-254">Rapport de configuration</span><span class="sxs-lookup"><span data-stu-id="69c01-254">Configuration Reporting</span></span>  
 <span data-ttu-id="69c01-255">Pour analyser correctement la configuration utilisée par une conversation, exécutez un rapport de configuration **ssbdiagnose** utilisant les mêmes options que celles de la conversation.</span><span class="sxs-lookup"><span data-stu-id="69c01-255">To correctly analyze the configuration used by a conversation, run a **ssbdiagnose** configuration report that uses the same options that are used by the conversation.</span></span> <span data-ttu-id="69c01-256">Si vous spécifiez pour **ssbdiagnose** un niveau d’options inférieur à celui de la conversation, **ssbdiagnose** risque de ne pas signaler les éléments requis par la conversation.</span><span class="sxs-lookup"><span data-stu-id="69c01-256">If you specify a lower level of options for **ssbdiagnose** than are used by the conversation, **ssbdiagnose** might not report conditions that are required by the conversation.</span></span> <span data-ttu-id="69c01-257">Si vous spécifiez un niveau d’options supérieur pour **ssbdiagnose**, ce dernier risque de signaler des éléments de rapport qui ne sont pas requis par la conversation.</span><span class="sxs-lookup"><span data-stu-id="69c01-257">If you specify a higher level of options for **ssbdiagnose**, it might report items that are not required by the conversation.</span></span> <span data-ttu-id="69c01-258">Par exemple, une conversation entre deux services qui se trouvent dans la même base de données peut être exécutée avec ENCPRYPTION OFF.</span><span class="sxs-lookup"><span data-stu-id="69c01-258">For example, a conversation between two services in the same database can be run with ENCPRYPTION OFF.</span></span> <span data-ttu-id="69c01-259">Si vous exécutez **ssbdiagnose** pour valider la configuration entre les deux services, mais utilisez le paramètre ENCRYPTION ON par défaut, **ssbdiagnose** signale qu’une clé principale est absente de la base de données.</span><span class="sxs-lookup"><span data-stu-id="69c01-259">If you run **ssbdiagnose** to validate the configuration between the two services, but use the default ENCRYPTION ON setting, **ssbdiagnose** reports that the database is missing a master key.</span></span> <span data-ttu-id="69c01-260">Or la conversation ne requiert pas de clé principale.</span><span class="sxs-lookup"><span data-stu-id="69c01-260">A master key is not required for the conversation.</span></span>  
  
 <span data-ttu-id="69c01-261">Le rapport de configuration de **ssbdiagnose** analyse un seul service [!INCLUDE[ssSB](../../includes/sssb-md.md)] ou une seule paire de services à chaque exécution.</span><span class="sxs-lookup"><span data-stu-id="69c01-261">The **ssbdiagnose** configuration report analyzes only one [!INCLUDE[ssSB](../../includes/sssb-md.md)] service or a single pair of services every time it is run.</span></span> <span data-ttu-id="69c01-262">Pour générer un rapport sur plusieurs paires de services [!INCLUDE[ssSB](../../includes/sssb-md.md)] , générez un fichier de commande .cmd qui appelle **ssbdiagnose** plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="69c01-262">To report on multiple pairs of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services, build a .cmd command file that calls **ssbdiagnose** multiple times.</span></span>  
  
## <a name="runtime-reporting"></a><span data-ttu-id="69c01-263">Rapport d'exécution</span><span class="sxs-lookup"><span data-stu-id="69c01-263">Runtime Reporting</span></span>  
 <span data-ttu-id="69c01-264">Quand vous spécifiez -RUNTIME, **ssbdiagnose** recherche toutes les bases de données spécifiées dans **runtimeconnectionoptions** et **baseconnectionoptions** pour générer la liste des ID [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69c01-264">When -RUNTIME is specified, **ssbdiagnose** searches all databases specified in **runtimeconnectionoptions** and **baseconnectionoptions** to build a list of [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs.</span></span> <span data-ttu-id="69c01-265">Le contenu de liste d'ID générée dépend des options -NEW et –ID :</span><span class="sxs-lookup"><span data-stu-id="69c01-265">The full list of IDs built depends on what is specified for -NEW and -ID:</span></span>  
  
-   <span data-ttu-id="69c01-266">Si vous ne spécifiez ni **-NEW** ni **-ID** , la liste inclut toutes les conversations pour toutes les bases de données spécifiées dans les options de connexion.</span><span class="sxs-lookup"><span data-stu-id="69c01-266">If neither **-NEW** or **-ID** are specified, the list includes all conversations for all databases specified in the connection options.</span></span>  
  
-   <span data-ttu-id="69c01-267">Si vous spécifiez **-NEW** , **ssbdiagnose** inclut les éléments de la première conversation qui démarre après exécution de **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="69c01-267">If **-NEW** is specified, **ssbdiagnose** includes the elements for the first conversation that starts after **ssbdiagnose** is run.</span></span> <span data-ttu-id="69c01-268">Sont ainsi inclus l'ID de la conversation et les descripteurs de la conversation pour les points de terminaison initiateur et cible.</span><span class="sxs-lookup"><span data-stu-id="69c01-268">This includes the conversation ID and the conversation handles for both the target and initiator conversation endpoints.</span></span>  
  
-   <span data-ttu-id="69c01-269">Si vous spécifiez **-ID** avec un descripteur de conversation, seul ce descripteur est inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="69c01-269">If **-ID** is specified with a conversation handle, only that handle is included in the list.</span></span>  
  
-   <span data-ttu-id="69c01-270">Si vous spécifiez **-ID** avec un ID de conversation, l’ID de conversation et les descripteurs de ses deux points de terminaison de conversation sont ajoutés à la liste.</span><span class="sxs-lookup"><span data-stu-id="69c01-270">If **-ID** is specified with a conversation ID, the conversation ID and the handles for both of its conversation endpoints are added to the list.</span></span>  
  
-   <span data-ttu-id="69c01-271">Si vous spécifiez **-ID** avec un ID de groupe de conversations, tous les ID de conversation et les descripteurs de conversation de ce groupe sont ajoutés à la liste.</span><span class="sxs-lookup"><span data-stu-id="69c01-271">If **-ID** is specified with a conversation group ID, all the conversation IDs and conversation handles in that group are added to the list.</span></span>  
  
 <span data-ttu-id="69c01-272">La liste n'inclut pas les éléments provenant de bases de données qui ne sont pas couvertes par les options de connexion.</span><span class="sxs-lookup"><span data-stu-id="69c01-272">The list does not include elements from databases that are not covered by the connection options.</span></span> <span data-ttu-id="69c01-273">Par exemple, supposons que vous utilisez **-ID** pour spécifier un ID de conversation, mais que vous ne fournissez une clause **runtimeconnectionoptions** que pour la base de données initiateur et pas pour la base de données cible.</span><span class="sxs-lookup"><span data-stu-id="69c01-273">For example, assume that you use **-ID** to specify a conversation ID, but only provide a **runtimeconnectionoptions** clause for the initiator database and not the target database.</span></span> <span data-ttu-id="69c01-274">**ssbdiagnose** n’inclut pas le descripteur de la conversation cible dans sa liste d’ID. Seuls l’ID de conversation et le descripteur de la conversation initiateur sont inclus.</span><span class="sxs-lookup"><span data-stu-id="69c01-274">**ssbdiagnose** will not include the target conversation handle in its list of IDs, only the conversation ID and the initiator conversation handle.</span></span>  
  
 <span data-ttu-id="69c01-275">**ssbdiagnose** analyse les événements [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] des bases de données couvertes par **runtimeconnectionoptions** et **baseconnectionoptions**.</span><span class="sxs-lookup"><span data-stu-id="69c01-275">**ssbdiagnose** monitors the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events from the databases covered by **runtimeconnectionoptions** and **baseconnectionoptions**.</span></span> <span data-ttu-id="69c01-276">Il recherche des événements [!INCLUDE[ssSB](../../includes/sssb-md.md)] indiquant qu’une erreur a été rencontrée par une ou plusieurs ID [!INCLUDE[ssSB](../../includes/sssb-md.md)] dans la liste d’exécution.</span><span class="sxs-lookup"><span data-stu-id="69c01-276">It searches for [!INCLUDE[ssSB](../../includes/sssb-md.md)] events that indicate an error was encountered by one or more of the [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs in the runtime list.</span></span> <span data-ttu-id="69c01-277">**ssbdiagnose** recherche également des événements d’erreur [!INCLUDE[ssSB](../../includes/sssb-md.md)] au niveau du système qui ne sont pas spécifiquement associés à un groupe de conversations.</span><span class="sxs-lookup"><span data-stu-id="69c01-277">**ssbdiagnose** also searches for system-level [!INCLUDE[ssSB](../../includes/sssb-md.md)] error events not specifically associated with any conversation group.</span></span>  
  
 <span data-ttu-id="69c01-278">Si **ssbdiagnose** détecte des erreurs de conversation, l’utilitaire tente de générer un rapport sur la cause première des événements en exécutant également un rapport de configuration.</span><span class="sxs-lookup"><span data-stu-id="69c01-278">If **ssbdiagnose** finds conversation errors, the utility will attempt to report on the root cause of the events by also running a configuration report.</span></span> <span data-ttu-id="69c01-279">**ssbdiagnose** utilise les métadonnées des bases de données pour essayer de déterminer les instances, les ID [!INCLUDE[ssSB](../../includes/sssb-md.md)] , les bases de données, les services et les contrats utilisés par la conversation.</span><span class="sxs-lookup"><span data-stu-id="69c01-279">**ssbdiagnose** uses the metadata in the databases to try to determine the instances, [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs, databases, services, and contracts used by the conversation.</span></span> <span data-ttu-id="69c01-280">Il exécute ensuite un rapport de configuration à l'aide de toutes les informations disponibles.</span><span class="sxs-lookup"><span data-stu-id="69c01-280">It then runs a configuration report using all available information.</span></span>  
  
 <span data-ttu-id="69c01-281">Par défaut, **ssbdiagnose** ne signale pas les événements d’erreur.</span><span class="sxs-lookup"><span data-stu-id="69c01-281">By default, **ssbdiagnose** does not report error events.</span></span> <span data-ttu-id="69c01-282">Il signale seulement les problèmes sous-jacents identifiés au cours de la vérification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="69c01-282">It only reports the underlying issues found during the configuration check.</span></span> <span data-ttu-id="69c01-283">Cela réduit la quantité d'informations signalée et vous aide à vous concentrer sur les problèmes de configuration sous-jacents.</span><span class="sxs-lookup"><span data-stu-id="69c01-283">This minimizes the amount of information reported and helps you focus on the underlying configuration issues.</span></span> <span data-ttu-id="69c01-284">Vous pouvez spécifier **-SHOWEVENTS** pour afficher les événements d’erreur rencontrés par **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="69c01-284">You can specify **-SHOWEVENTS** to see the error events encountered by **ssbdiagnose**.</span></span>  
  
## <a name="issues-reported-by-ssbdiagnose"></a><span data-ttu-id="69c01-285">Problèmes signalés par ssbdiagnose</span><span class="sxs-lookup"><span data-stu-id="69c01-285">Issues Reported by ssbdiagnose</span></span>  
 <span data-ttu-id="69c01-286">**ssbdiagnose** signale trois classes de problèmes.</span><span class="sxs-lookup"><span data-stu-id="69c01-286">**ssbdiagnose** reports three classes of issues.</span></span> <span data-ttu-id="69c01-287">Dans le fichier de sortie XML, chaque catégorie de problème correspond à un type distinct de l'élément Issue.</span><span class="sxs-lookup"><span data-stu-id="69c01-287">In the XML output file, each class of issue is reported as a separate type of the Issue element.</span></span> <span data-ttu-id="69c01-288">Ces trois types de problèmes signalés par **ssbdiagnose** sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="69c01-288">The three types of issues reported by **ssbdiagnose** are as follows:</span></span>  
  
 <span data-ttu-id="69c01-289">**Diagnostic**</span><span class="sxs-lookup"><span data-stu-id="69c01-289">**Diagnosis**</span></span>  
 <span data-ttu-id="69c01-290">Signale un problème de configuration.</span><span class="sxs-lookup"><span data-stu-id="69c01-290">Reports a configuration issue.</span></span> <span data-ttu-id="69c01-291">Sont inclus les problèmes identifiés soit lors de l’exécution d’un rapport **CONFIGURATION** , soit pendant la phase de configuration d’un rapport **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="69c01-291">This includes issues found either a **CONFIGURATION** report is running, or during the configuration phase of a **RUNTIME** report.</span></span> <span data-ttu-id="69c01-292">**ssbdiagnose** signale chaque problème de configuration une seule fois.</span><span class="sxs-lookup"><span data-stu-id="69c01-292">**ssbdiagnose** reports each configuration issue one time.</span></span>  
  
 <span data-ttu-id="69c01-293">**Event**</span><span class="sxs-lookup"><span data-stu-id="69c01-293">**Event**</span></span>  
 <span data-ttu-id="69c01-294">Signale un événement [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] qui indique qu’un problème a été rencontré par une conversation surveillée pendant un rapport **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="69c01-294">Reports a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] event that indicates a problem was encountered by a conversation being monitored during a **RUNTIME** report.</span></span> <span data-ttu-id="69c01-295">**ssbdiagnose** signale les événements chaque fois qu’ils sont générés.</span><span class="sxs-lookup"><span data-stu-id="69c01-295">**ssbdiagnose** reports events every time they are generated.</span></span> <span data-ttu-id="69c01-296">Les événements peuvent être signalés plusieurs fois si plusieurs conversations rencontrent le problème.</span><span class="sxs-lookup"><span data-stu-id="69c01-296">Events can be reported multiple times if several conversations encounter the problem.</span></span>  
  
 <span data-ttu-id="69c01-297">**Problème**</span><span class="sxs-lookup"><span data-stu-id="69c01-297">**Problem**</span></span>  
 <span data-ttu-id="69c01-298">Signale un problème qui empêche **ssbdiagnose** d’effectuer une analyse de la configuration ou de surveiller des conversations.</span><span class="sxs-lookup"><span data-stu-id="69c01-298">Reports an issue that is preventing **ssbdiagnose** from completing a configuration analysis or from monitoring conversations.</span></span>  
  
## <a name="sqlcmd-environment-variables"></a><span data-ttu-id="69c01-299">Variables d'environnement sqlcmd</span><span class="sxs-lookup"><span data-stu-id="69c01-299">sqlcmd Environment Variables</span></span>  
 <span data-ttu-id="69c01-300">L’utilitaire **ssbdiagnose** prend en charge les variables d’environnement SQLCMDSERVER, SQLCMDUSER, SQLCMDPASSWORD et SQLCMDLOGINTIMOUT, qui sont également utilisées par l’utilitaire **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="69c01-300">The **ssbdiagnose** utility supports the SQLCMDSERVER, SQLCMDUSER, SQLCMDPASSWORD, and SQLCMDLOGINTIMOUT environment variables that are also used by the **sqlcmd** utility.</span></span> <span data-ttu-id="69c01-301">Vous pouvez définir les variables d’environnement soit en utilisant l’invite de commandes SET, soit en utilisant la commande **setvar** dans des scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutés à l’aide de **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="69c01-301">You can set the environment variables either by using the command prompt SET command, or by using the **setvar** command in [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that you run by using **sqlcmd**.</span></span> <span data-ttu-id="69c01-302">Pour plus d’informations sur la façon d’utiliser **setvar** dans **sqlcmd**, consultez [Utiliser sqlcmd avec des variables de script](../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="69c01-302">For more information about how to use **setvar** in **sqlcmd**, see [Use sqlcmd with Scripting Variables](../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="69c01-303">Autorisations</span><span class="sxs-lookup"><span data-stu-id="69c01-303">Permissions</span></span>  
 <span data-ttu-id="69c01-304">Dans chaque clause **connectionoptions** , la connexion spécifiée avec l’option **-E** ou **-U** doit être un membre du rôle serveur fixe **sysadmin** dans l’instance spécifiée dans **-S**.</span><span class="sxs-lookup"><span data-stu-id="69c01-304">In each **connectionoptions** clause, the login specified with either **-E** or **-U** must be a member of the **sysadmin** fixed-server role in the instance specified in **-S**.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="69c01-305">Exemples</span><span class="sxs-lookup"><span data-stu-id="69c01-305">Examples</span></span>  
 <span data-ttu-id="69c01-306">Cette section contient des exemples d’utilisation de **ssbdiagnose** à une invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="69c01-306">This section contains examples of using **ssbdiagnose** at a command prompt.</span></span>  
  
### <a name="a-checking-the-configuration-of-two-services-in-the-same-database"></a><span data-ttu-id="69c01-307">R.</span><span class="sxs-lookup"><span data-stu-id="69c01-307">A.</span></span> <span data-ttu-id="69c01-308">Vérification de la configuration de deux services dans la même base de données</span><span class="sxs-lookup"><span data-stu-id="69c01-308">Checking the Configuration of Two Services in the Same Database</span></span>  
 <span data-ttu-id="69c01-309">L'exemple suivant montre comment demander un rapport de configuration dans le contexte suivant :</span><span class="sxs-lookup"><span data-stu-id="69c01-309">The following example shows how to request a configuration report when the following are true;</span></span>  
  
-   <span data-ttu-id="69c01-310">Le service initiateur et le service cible se trouvent dans la même base de données.</span><span class="sxs-lookup"><span data-stu-id="69c01-310">The initiator and target service are in the same database.</span></span>  
  
-   <span data-ttu-id="69c01-311">La base de données se trouve dans l'instance par défaut du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69c01-311">The database is in the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="69c01-312">Les instances se trouvent sur l’ordinateur sur lequel **ssbdiagnose** est exécuté.</span><span class="sxs-lookup"><span data-stu-id="69c01-312">The instances is on the same computer on which **ssbdiagnose** is run.</span></span>  
  
 <span data-ttu-id="69c01-313">L’utilitaire **ssbdiagnose** signale la configuration qui utilise le contrat DEFAULT, car ON CONTRACT n’est pas spécifié.</span><span class="sxs-lookup"><span data-stu-id="69c01-313">The **ssbdiagnose** utility reports the configuration that uses the DEFAULT contract because ON CONTRACT is not specified.</span></span>  
  
```  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE /test/initiator TO SERVICE /test/target  
```  
  
### <a name="b-checking-the-configuration-of-two-services-on-separate-computers-that-use-one-login"></a><span data-ttu-id="69c01-314">B.</span><span class="sxs-lookup"><span data-stu-id="69c01-314">B.</span></span> <span data-ttu-id="69c01-315">Vérification de la configuration de deux services sur des ordinateurs distincts qui utilisent une seule connexion</span><span class="sxs-lookup"><span data-stu-id="69c01-315">Checking the Configuration of Two Services on Separate Computers That Use One Login</span></span>  
 <span data-ttu-id="69c01-316">L'exemple suivant montre comment demander un rapport de configuration lorsque le service initiateur et le service cible se trouvent sur des ordinateurs distincts, mais sont accessibles en utilisant la même connexion via l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="69c01-316">The following example shows how to request a configuration report when the initiator and target service are on separate computers, but can be accessed by using the same Windows Authentication login.</span></span>  
  
```  
ssbdiagnose -E CONFIGURATION FROM SERVICE /text/initiator -S InitiatorComputer -d InitiatorDatabase TO SERVICE /test/target -S TargetComputer -d TargetDatabase ON CONTRACT TestContract  
```  
  
### <a name="c-checking-the-configuration-of-two-services-on-separate-computers-that-use-separate-logins"></a><span data-ttu-id="69c01-317">C.</span><span class="sxs-lookup"><span data-stu-id="69c01-317">C.</span></span> <span data-ttu-id="69c01-318">Vérification de la configuration de deux services sur des ordinateurs distincts qui utilisent des connexions distinctes</span><span class="sxs-lookup"><span data-stu-id="69c01-318">Checking the Configuration of Two Services on Separate Computers That Use Separate Logins</span></span>  
 <span data-ttu-id="69c01-319">L'exemple suivant montre comment demander un rapport de configuration lorsque le service initiateur et le service cible se trouvent sur des ordinateurs distincts et que des connexions d'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] distinctes sont requises pour chaque instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69c01-319">The following example shows how to request a configuration report when the initiator and target service are on separate computers, and separate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication logins are required for each instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
```  
ssbdiagnose CONFIGURATION FROM SERVICE /text/initiator   
-S InitiatorComputer -U InitiatorLogin -p !wEx23Dvb   
-d InitiatorDatabase TO SERVICE /test/target -S TargetComputer   
-U TargetLogin -p ER!49jiy -d TargetDatabase ON CONTRACT TestContract  
```  
  
### <a name="d-checking-mirrored-service-configurations-on-separate-computers-with-anonymous-encryption"></a><span data-ttu-id="69c01-320">D.</span><span class="sxs-lookup"><span data-stu-id="69c01-320">D.</span></span> <span data-ttu-id="69c01-321">Vérification de la configuration de services mis en miroir sur des ordinateurs distincts avec le chiffrement anonyme</span><span class="sxs-lookup"><span data-stu-id="69c01-321">Checking Mirrored Service Configurations on Separate Computers With Anonymous Encryption</span></span>  
 <span data-ttu-id="69c01-322">L'exemple suivant montre comment demander un rapport de configuration lorsque le service initiateur et le service cible se trouvent sur des ordinateurs distincts et que l'initiateur est mis en miroir sur une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="69c01-322">The following example shows how to request a configuration report when the initiator and target service are on separate computers and the initiator is mirrored to a named instance.</span></span> <span data-ttu-id="69c01-323">Ce rapport vérifie également que les services sont configurés pour utiliser le chiffrement anonyme.</span><span class="sxs-lookup"><span data-stu-id="69c01-323">The report also verifies that the services are configured to use anonymous encryption.</span></span>  
  
```  
ssbdiagnose -E CONFIGURATION FROM SERVICE /text/initiator   
-S InitiatorComputer -d InitiatorDatabase MIRROR   
-S MirrorComputer/MirrorInstance TO SERVICE /test/target   
-S TargetComputer -d TargetDatabase ON CONTRACT TestContract ENCRYPTION ANONYMOUS  
```  
  
### <a name="e-checking-the-configuration-of-two-contracts"></a><span data-ttu-id="69c01-324">E.</span><span class="sxs-lookup"><span data-stu-id="69c01-324">E.</span></span> <span data-ttu-id="69c01-325">Vérification de la configuration de deux contrats</span><span class="sxs-lookup"><span data-stu-id="69c01-325">Checking the Configuration of Two Contracts</span></span>  
 <span data-ttu-id="69c01-326">L'exemple suivant montre comment générer un fichier de commandes qui demande des rapports de configuration dans le contexte suivant :</span><span class="sxs-lookup"><span data-stu-id="69c01-326">The following example shows how to build a command file that requests configuration reports when the following are true:</span></span>  
  
-   <span data-ttu-id="69c01-327">Le service initiateur et le service cible se trouvent dans la même base de données.</span><span class="sxs-lookup"><span data-stu-id="69c01-327">The initiator and target service are in the same database.</span></span>  
  
-   <span data-ttu-id="69c01-328">La base de données se trouve dans l'instance par défaut du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69c01-328">The database is in the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="69c01-329">L’instance se trouve sur l’ordinateur sur lequel **ssbdiagnose** est exécuté.</span><span class="sxs-lookup"><span data-stu-id="69c01-329">The instance is on the same computer on which **ssbdiagnose** is run.</span></span>  
  
 <span data-ttu-id="69c01-330">À chaque exécution, **ssbdiagnose** signale la configuration d’un contrat différent entre les mêmes services.</span><span class="sxs-lookup"><span data-stu-id="69c01-330">Each time **ssbdiagnose** is run it reports the configuration for a different contract between the same services.</span></span>  
  
```  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target ON CONTRACT PayRaiseContract  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE /test/initiator   
TO SERVICE /test/target ON CONTRACT PromotionContract  
```  
  
### <a name="f-monitor-the-status-of-a-specific-conversation-on-the-local-computer-with-a-time-out"></a><span data-ttu-id="69c01-331">F.</span><span class="sxs-lookup"><span data-stu-id="69c01-331">F.</span></span> <span data-ttu-id="69c01-332">Surveillance du statut d'une conversation spécifique sur l'ordinateur local avec un délai d'attente</span><span class="sxs-lookup"><span data-stu-id="69c01-332">Monitor the status of a specific conversation on the local computer with a time out</span></span>  
 <span data-ttu-id="69c01-333">L’exemple suivant montre comment surveiller une conversation spécifique où le service initiateur et le service cible se trouvent dans la même base de données dans l’instance par défaut du même ordinateur exécutant **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="69c01-333">The following example shows how to monitor a specific conversation where the initiator and target services are in the same database in the default instance of the same computer that is running **ssbdiagnose**.</span></span> <span data-ttu-id="69c01-334">La valeur de l'intervalle d'arrêt est de 20 secondes.</span><span class="sxs-lookup"><span data-stu-id="69c01-334">The time-out interval is set to 20 seconds.</span></span>  
  
```  
ssbdiagnose -E -d TestDatabase RUNTIME -ID D68D77A9-B1CF-41BF-A5CE-279ABCAB140D -TIMEOUT 20  
```  
  
### <a name="g-monitor-the-status-of-a-conversation-that-spans-two-computers"></a><span data-ttu-id="69c01-335">G.</span><span class="sxs-lookup"><span data-stu-id="69c01-335">G.</span></span> <span data-ttu-id="69c01-336">Surveillance du statut d'une conversation qui s'étend sur deux ordinateurs</span><span class="sxs-lookup"><span data-stu-id="69c01-336">Monitor the status of a conversation that spans two computers</span></span>  
 <span data-ttu-id="69c01-337">L'exemple suivant montre comment surveiller une conversation spécifique où le service initiateur et le service cible se trouvent sur des ordinateurs distincts.</span><span class="sxs-lookup"><span data-stu-id="69c01-337">The following example shows how to monitor a specific conversation where the initiator and target services are on separate computers.</span></span>  
  
```  
ssbdiagnose RUNTIME -ID D68D77A9-B1CF-41BF-A5CE-279ABCAB140D   
-TIMEOUT 10 CONNECT TO -E -S InitiatorComputer/InitiatorInstance   
-d InitiatorDatabase CONNECT TO -E -S TargetComputer/TargetInstance   
-d TargetDatabase  
```  
  
### <a name="h-monitor-the-status-of-a-conversation-in-two-databases-in-the-same-instance"></a><span data-ttu-id="69c01-338">H.</span><span class="sxs-lookup"><span data-stu-id="69c01-338">H.</span></span> <span data-ttu-id="69c01-339">Surveillance du statut d'une conversation dans deux bases de données dans la même instance</span><span class="sxs-lookup"><span data-stu-id="69c01-339">Monitor the status of a conversation in two databases in the same instance</span></span>  
 <span data-ttu-id="69c01-340">L'exemple suivant montre comment surveiller une conversation spécifique où le service initiateur et le service cible se trouvent dans des bases de données distinctes dans la même instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69c01-340">The following example shows how to monitor a specific conversation where the initiator and target services are in separate databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="69c01-341">Cet exemple utilise **baseconnectionoptions** pour spécifier l’instance et les informations de connexion, ainsi que deux clauses CONNECT TO pour spécifier les bases de données.</span><span class="sxs-lookup"><span data-stu-id="69c01-341">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span> <span data-ttu-id="69c01-342">-SHOWEVENTS est spécifié afin que tous les événements d'exécution soient inclus dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="69c01-342">-SHOWEVENTS is specified so that all runtime events are included in the report output.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME -SHOWEVENTS   
-ID 5094d4a7-e38c-4c37-da37-1d58b1cb8455 -TIMEOUT 10 CONNECT TO   
-d InitiatorDatabase CONNECT TO -d TargetDatabase  
```  
  
### <a name="i-monitor-the-status-of-two-conversations-between-two-databases"></a><span data-ttu-id="69c01-343">I.</span><span class="sxs-lookup"><span data-stu-id="69c01-343">I.</span></span> <span data-ttu-id="69c01-344">Surveillance du statut de deux conversations entre deux bases de données</span><span class="sxs-lookup"><span data-stu-id="69c01-344">Monitor the status of two conversations between two databases</span></span>  
 <span data-ttu-id="69c01-345">L'exemple suivant montre comment surveiller deux conversations spécifiques où le service initiateur et le service cible se trouvent dans des bases de données distinctes dans la même instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69c01-345">The following example shows how to monitor two conversations where the initiator and target services are in separate databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="69c01-346">Cet exemple utilise **baseconnectionoptions** pour spécifier l’instance et les informations de connexion, ainsi que deux clauses CONNECT TO pour spécifier les bases de données.</span><span class="sxs-lookup"><span data-stu-id="69c01-346">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME   
-ID 5094d4a7-e38c-4c37-da37-1d58b1cb8455   
-ID 9b293be9-226b-4e22-e169-1d2c2c15be86 -TIMEOUT 10 CONNECT TO   
-d InitiatorDatabase CONNECT TO -d TargetDatabase  
```  
  
### <a name="j-monitor-the-status-of-all-conversations-between-two-databases"></a><span data-ttu-id="69c01-347">J.</span><span class="sxs-lookup"><span data-stu-id="69c01-347">J.</span></span> <span data-ttu-id="69c01-348">Surveillance du statut de toutes les conversations entre deux bases de données</span><span class="sxs-lookup"><span data-stu-id="69c01-348">Monitor the status of all conversations between two databases</span></span>  
 <span data-ttu-id="69c01-349">L'exemple suivant montre comment surveiller toutes les conversations entre deux bases de données dans la même instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69c01-349">The following example shows how to monitor all the conversation between two databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="69c01-350">Cet exemple utilise **baseconnectionoptions** pour spécifier l’instance et les informations de connexion, ainsi que deux clauses CONNECT TO pour spécifier les bases de données.</span><span class="sxs-lookup"><span data-stu-id="69c01-350">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME   
-TIMEOUT 10 CONNECT TO -d InitiatorDatabase CONNECT TO   
-d TargetDatabase  
```  
  
### <a name="k-ignore-specific-errors"></a><span data-ttu-id="69c01-351">K.</span><span class="sxs-lookup"><span data-stu-id="69c01-351">K.</span></span> <span data-ttu-id="69c01-352">Ignorer des erreurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="69c01-352">Ignore Specific Errors</span></span>  
 <span data-ttu-id="69c01-353">L'exemple suivant montre comment ignorer les erreurs connues (303 et 304) détectées dans la configuration actuelle de l'activation dans un système test.</span><span class="sxs-lookup"><span data-stu-id="69c01-353">The following example shows how to ignore known errors (303 and 304) in how activation is currently configured in a test system.</span></span>  
  
```  
ssbdiagnose -IGNORE 303 -IGNORE 304 -E -d TestDatabase   
CONFIGURATION FROM SERVICE /test/initiator TO SERVICE /test/target   
ON CONTRACT TextContract  
```  
  
### <a name="l-redirecting-ssbdiagnose-xml-output"></a><span data-ttu-id="69c01-354">L.</span><span class="sxs-lookup"><span data-stu-id="69c01-354">L.</span></span> <span data-ttu-id="69c01-355">Redirection de la sortie XML de ssbdiagnose</span><span class="sxs-lookup"><span data-stu-id="69c01-355">Redirecting ssbdiagnose XML Output</span></span>  
 <span data-ttu-id="69c01-356">L’exemple suivant montre comment demander que **ssbdiagnose** génère sa sortie sous la forme d’un fichier XML redirigé vers un fichier.</span><span class="sxs-lookup"><span data-stu-id="69c01-356">The following example shows how to request that **ssbdiagnose** generate its output as an XML file that is redirected to a file.</span></span> <span data-ttu-id="69c01-357">Le fichier TestDiag.xml peut ensuite être ouvert par une application pour analyser ou créer un rapport à partir des fichiers XML de **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="69c01-357">The TestDiag.xml file can then be opened by an application to analyze or report **ssbdiagnose** XML files.</span></span> <span data-ttu-id="69c01-358">Vous pouvez également le consulter dans tout éditeur XML, tel que le bloc-notes XML.</span><span class="sxs-lookup"><span data-stu-id="69c01-358">Or, you can view it from a general XML editor such as XML Notepad.</span></span>  
  
```  
ssbdiagnose -XML -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target > c:\MyDiagnostics\TestDiag.xml  
```  
  
### <a name="m-using-an-environment-variable"></a><span data-ttu-id="69c01-359">M.</span><span class="sxs-lookup"><span data-stu-id="69c01-359">M.</span></span> <span data-ttu-id="69c01-360">Utilisation d'une variable d'environnement</span><span class="sxs-lookup"><span data-stu-id="69c01-360">Using an Environment Variable</span></span>  
 <span data-ttu-id="69c01-361">L’exemple suivant commence par définir la variable d’environnement SQLCMDSERVER pour qu’elle contienne le nom du serveur, puis exécute **ssbdiagnose** sans spécifier l’option **-S**.</span><span class="sxs-lookup"><span data-stu-id="69c01-361">The following example first sets the SQLCMDSERVER environment variable to hold the server name, and then runs **ssbdiagnose** without specifying **-S**.</span></span>  
  
```  
SET SQLCMDSERVER=MyComputer  
ssbdiagnose -XML -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target  
```  
  
## <a name="see-also"></a><span data-ttu-id="69c01-362">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="69c01-362">See Also</span></span>  
 <span data-ttu-id="69c01-363">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span><span class="sxs-lookup"><span data-stu-id="69c01-363">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span></span>  
 <span data-ttu-id="69c01-364">[BEGIN DIALOG CONVERSATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/begin-dialog-conversation-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-364">[BEGIN DIALOG CONVERSATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/begin-dialog-conversation-transact-sql) </span></span>  
 <span data-ttu-id="69c01-365">[CREATE BROKER PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-broker-priority-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-365">[CREATE BROKER PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-broker-priority-transact-sql) </span></span>  
 <span data-ttu-id="69c01-366">[CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-366">[CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql) </span></span>  
 <span data-ttu-id="69c01-367">[CREATE CONTRACT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-contract-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-367">[CREATE CONTRACT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-contract-transact-sql) </span></span>  
 <span data-ttu-id="69c01-368">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-368">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="69c01-369">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-369">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span></span>  
 <span data-ttu-id="69c01-370">[CREATE MESSAGE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-message-type-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-370">[CREATE MESSAGE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-message-type-transact-sql) </span></span>  
 <span data-ttu-id="69c01-371">[CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-371">[CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) </span></span>  
 <span data-ttu-id="69c01-372">[CREATE REMOTE SERVICE BINDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-remote-service-binding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-372">[CREATE REMOTE SERVICE BINDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-remote-service-binding-transact-sql) </span></span>  
 <span data-ttu-id="69c01-373">[CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-373">[CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql) </span></span>  
 <span data-ttu-id="69c01-374">[CREATE SERVICE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-service-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-374">[CREATE SERVICE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-service-transact-sql) </span></span>  
 <span data-ttu-id="69c01-375">[RECEIVE &#40;Transact-SQL&#41;](/sql/t-sql/statements/receive-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-375">[RECEIVE &#40;Transact-SQL&#41;](/sql/t-sql/statements/receive-transact-sql) </span></span>  
 <span data-ttu-id="69c01-376">[sys.transmission_queue &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-transmission-queue-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-376">[sys.transmission_queue &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-transmission-queue-transact-sql) </span></span>  
 <span data-ttu-id="69c01-377">[sys.conversation_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-conversation-endpoints-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c01-377">[sys.conversation_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-conversation-endpoints-transact-sql) </span></span>  
 [<span data-ttu-id="69c01-378">sys.conversation_groups &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="69c01-378">sys.conversation_groups &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-conversation-groups-transact-sql)  
  
  
