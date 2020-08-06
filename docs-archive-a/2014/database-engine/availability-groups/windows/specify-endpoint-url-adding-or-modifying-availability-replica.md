---
title: Spécifier l’URL du point de terminaison lors de l’ajout ou de la modification d’un réplica de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- endpoints [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], endpoint
- Endpoint URLs (HADR)
ms.assetid: d7520c13-a8ee-4ddc-9e9a-54cd3d27ef1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da1eb2bacd4d5a2f7d0b2a623343f62b5e89597d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708659"
---
# <a name="specify-the-endpoint-url-when-adding-or-modifying-an-availability-replica-sql-server"></a><span data-ttu-id="3e3e0-102">Spécifier l'URL de point de terminaison lors de l'ajout ou lors de la modification d'un réplica de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3e3e0-102">Specify the Endpoint URL When Adding or Modifying an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="3e3e0-103">Pour héberger un réplica de disponibilité pour un groupe de disponibilité, une instance de serveur doit posséder un point de terminaison de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-103">To host an availability replica for an availability group, a server instance must possess a database mirroring endpoint.</span></span> <span data-ttu-id="3e3e0-104">L'instance de serveur utilise ce point de terminaison pour écouter les messages [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] des réplicas de disponibilité hébergés par d'autres instances de serveur.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-104">The server instance uses this endpoint to listen for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] messages from availability replicas hosted by other server instances.</span></span> <span data-ttu-id="3e3e0-105">Pour définir un réplica de disponibilité pour un groupe de disponibilité, vous devez spécifier l'URL de point de terminaison de l'instance de serveur qui hébergera le réplica.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-105">To define an availability replica for an availability group, you must specify the endpoint URL of the server instance that will host the replica.</span></span> <span data-ttu-id="3e3e0-106">L’*URL de point de terminaison* identifie le protocole de transport du point de terminaison de mise en miroir de bases de données (TCP), l’adresse système de l’instance de serveur et le numéro de port associé au point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-106">The *endpoint URL* identifies the transport protocol of the database mirroring endpoint-TCP, the system address of the server instance, and the port number associated with the endpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e3e0-107">Le terme « URL de point de terminaison » est synonyme du terme « adresse réseau du serveur » qui est utilisé dans l'interface utilisateur et la documentation de la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-107">The term "endpoint URL" is synonymous with the term "server network address" used by the database mirroring user interface and documentation.</span></span>  
  
-   [<span data-ttu-id="3e3e0-108">Syntaxe pour une URL de point de terminaison</span><span class="sxs-lookup"><span data-stu-id="3e3e0-108">Syntax for an Endpoint URL</span></span>](#SyntaxOfURL)  
  
-   [<span data-ttu-id="3e3e0-109">Recherche du nom de domaine complet d’un système</span><span class="sxs-lookup"><span data-stu-id="3e3e0-109">Finding the Fully Qualified Domain Name of A System</span></span>](#Finding_FQDN)  
  
-   [<span data-ttu-id="3e3e0-110">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="3e3e0-110">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="3e3e0-111">Contenu connexe</span><span class="sxs-lookup"><span data-stu-id="3e3e0-111">Related Content</span></span>](#RelatedContent)  
  
##  <a name="syntax-for-an-endpoint-url"></a><a name="SyntaxOfURL"></a> <span data-ttu-id="3e3e0-112">Syntaxe pour une URL de point de terminaison</span><span class="sxs-lookup"><span data-stu-id="3e3e0-112">Syntax for an Endpoint URL</span></span>  
 <span data-ttu-id="3e3e0-113">La syntaxe d'une URL de point de terminaison est la suivante :</span><span class="sxs-lookup"><span data-stu-id="3e3e0-113">The syntax for an endpoint URL is of the form:</span></span>  
  
 <span data-ttu-id="3e3e0-114">TCP<strong>://</strong> *\<system-address>* <strong>:</strong> *\<port>*</span><span class="sxs-lookup"><span data-stu-id="3e3e0-114">TCP<strong>://</strong>*\<system-address>*<strong>:</strong>*\<port>*</span></span>  
  
 <span data-ttu-id="3e3e0-115">where</span><span class="sxs-lookup"><span data-stu-id="3e3e0-115">where</span></span>  
  
-   <span data-ttu-id="3e3e0-116">*\<system-address>* est une chaîne qui identifie sans ambiguïté le système informatique cible.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-116">*\<system-address>* is a string that unambiguously identifies the target computer system.</span></span> <span data-ttu-id="3e3e0-117">En règle générale, l'adresse de serveur est un nom système (si les systèmes sont dans le même domaine), un nom de domaine complet ou une adresse IP :</span><span class="sxs-lookup"><span data-stu-id="3e3e0-117">Typically, the server address is a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address:</span></span>  
  
    -   <span data-ttu-id="3e3e0-118">Étant donné que les nœuds du cluster WSFC (clustering de basculement Windows Server) figurent dans le même domaine, vous pouvez utiliser le nom du système informatique, par exemple `SYSTEM46`.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-118">Because the nodes of Windows Server Failover Clustering (WSFC) cluster are the same domain, you can use the name of the computer system; for example, `SYSTEM46`.</span></span>  
  
    -   <span data-ttu-id="3e3e0-119">Pour pouvoir utiliser une adresse IP, elle doit être unique dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-119">To use an IP address, it must be unique in your environment.</span></span> <span data-ttu-id="3e3e0-120">Nous vous recommandons d'utiliser une adresse IP seulement si elle est statique.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-120">We recommend that you use an IP address only if it is static.</span></span> <span data-ttu-id="3e3e0-121">L'adresse IP peut être une adresse IP Version 4 (IPv4) ou IP Version 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="3e3e0-121">The IP address can be IP Version 4 (IPv4) or IP Version 6 (IPv6).</span></span> <span data-ttu-id="3e3e0-122">Une adresse IPv6 doit être placée entre crochets, par exemple : **[** _<adresse_IPv6>_ **]** .</span><span class="sxs-lookup"><span data-stu-id="3e3e0-122">An IPv6 address must be enclosed within square brackets, for example: **[**_<IPv6_address>_**]**.</span></span>  
  
         <span data-ttu-id="3e3e0-123">Pour connaître l'adresse IP d'un système, à l'invite de commandes Windows, entrez la commande **ipconfig** .</span><span class="sxs-lookup"><span data-stu-id="3e3e0-123">To learn the IP address of a system, at the Windows command prompt, enter the **ipconfig** command.</span></span>  
  
    -   <span data-ttu-id="3e3e0-124">L'utilisation du nom de domaine complet garantit un fonctionnement correct.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-124">The fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="3e3e0-125">Il s'agit d'une chaîne d'adresse définie localement qui prend des formes différentes dans des emplacements différents.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-125">This is a locally defined address string that takes different forms in different places.</span></span> <span data-ttu-id="3e3e0-126">Souvent, mais pas systématiquement, un nom de domaine complet correspond à un nom composé qui inclut le nom de l'ordinateur et une série de segments de domaine séparés par des points, de la forme :</span><span class="sxs-lookup"><span data-stu-id="3e3e0-126">Often, but not always, a fully qualified domain name is a compound name that includes the computer name and a series of period-separated domain segments of the form:</span></span>  
  
         <span data-ttu-id="3e3e0-127">_nom_ordinateur_ **.**</span><span class="sxs-lookup"><span data-stu-id="3e3e0-127">_computer_name_ **.**</span></span> <span data-ttu-id="3e3e0-128">_segment_domaine_[... **.** _segment_domaine_]</span><span class="sxs-lookup"><span data-stu-id="3e3e0-128">_domain_segment_[...**.**_domain_segment_]</span></span>  
  
         <span data-ttu-id="3e3e0-129">où *nom_ordinateur*correspond au nom réseau de l’ordinateur qui exécute l’instance de serveur et *segment_domaine*[... **.** _segment_domaine_] représente les autres informations de domaine du serveur ; par exemple : `localinfo.corp.Adventure-Works.com`.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-129">where *computer_name i*s the network name of the computer running the server instance, and *domain_segment*[...**.**_domain_segment_] is the remaining domain information of the server; for example: `localinfo.corp.Adventure-Works.com`.</span></span>  
  
         <span data-ttu-id="3e3e0-130">Le contenu et le nombre de segments de domaine sont déterminés au sein de la société ou de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-130">The content and number of domain segments are determined within the company or organization.</span></span> <span data-ttu-id="3e3e0-131">Pour plus d'informations, consultez [Recherche du nom de domaine complet](#Finding_FQDN), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-131">For more information, see [Finding the Fully Qualified Domain Name](#Finding_FQDN), later in this topic.</span></span>  
  
-   <span data-ttu-id="3e3e0-132">*\<port>* est le numéro de port utilisé par le point de terminaison de mise en miroir de l'instance de serveur partenaire.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-132">*\<port>* is the port number used by the mirroring endpoint of the partner server instance.</span></span>  
  
     <span data-ttu-id="3e3e0-133">Un point de terminaison de mise en miroir de bases de données peut utiliser tout port disponible sur le système informatique.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-133">A database mirroring endpoint can use any available port on the computer system.</span></span> <span data-ttu-id="3e3e0-134">Chaque numéro de port doit être associé à un seul point de terminaison, et chaque point de terminaison est associé à une seule instance de serveur ; ainsi, différentes instances de serveurs sur le même serveur écoutent sur différents points de terminaison dotés de différents ports.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-134">Each port number must be associated with only one endpoint, and each endpoint is associated with a single server instance; thus, different server instances on the same server listen on different endpoints with different ports.</span></span> <span data-ttu-id="3e3e0-135">Par conséquent, le port que vous précisez dans l'URL de point de terminaison lorsque vous spécifiez un réplica de disponibilité dirigera toujours les messages entrants à l'instance de serveur dont le point de terminaison est associé à ce port.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-135">Therefore, the port you specify in the endpoint URL when you specify an availability replica will always direct incoming messages to the server instance whose endpoint is associated with that port.</span></span>  
  
     <span data-ttu-id="3e3e0-136">Dans l'URL de point de terminaison, seul le numéro du port identifie l'instance de serveur associée au point de terminaison de mise en miroir sur l'ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-136">IIn the endpoint URL, only the number of the port identifies the server instance that is associated with the mirroring endpoint on the target computer.</span></span> <span data-ttu-id="3e3e0-137">L'illustration suivante présente les URL de point de terminaison de deux instances de serveurs sur un même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-137">The following figure illustrates the endpoint URLs of two server instances on a single computer.</span></span> <span data-ttu-id="3e3e0-138">L'instance par défaut utilise le port `7022` et l'instance nommée utilise le port `7033`.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-138">The default instance uses port `7022` and the named instance uses port `7033`.</span></span> <span data-ttu-id="3e3e0-139">L'URL de point de terminaison de ces deux instances de serveur sont, respectivement : `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` et `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-139">The endpoint URL for these two server instances are, respectively: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` and `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span></span> <span data-ttu-id="3e3e0-140">Notez que l'adresse ne contient pas le nom de l'instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-140">Note that the address does not contain the name of the server instance.</span></span>  
  
     <span data-ttu-id="3e3e0-141">![Adresses réseau de serveur d’une instance par défaut](../../media/dbm-2-instances-ports-1-system.gif "Adresses réseau de serveur d’une instance par défaut")</span><span class="sxs-lookup"><span data-stu-id="3e3e0-141">![Server network addresses of a default instance](../../media/dbm-2-instances-ports-1-system.gif "Server network addresses of a default instance")</span></span>  
  
     <span data-ttu-id="3e3e0-142">Pour identifier le port actuellement associé au point de terminaison de mise en miroir de bases de données d'une instance de serveur, utilisez l'instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] suivante :</span><span class="sxs-lookup"><span data-stu-id="3e3e0-142">To identify the port currently associated with database mirroring endpoint of a server instance, use the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql
    SELECT type_desc, port FROM sys.TCP_endpoints  
    ```  
  
     <span data-ttu-id="3e3e0-143">Recherchez la ligne dont la valeur **type_desc** est « DATABASE_MIRRORING » et utilisez le numéro de port correspondant.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-143">Find the row whose **type_desc** value is "DATABASE_MIRRORING," and use the corresponding port number.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="3e3e0-144">Exemples</span><span class="sxs-lookup"><span data-stu-id="3e3e0-144">Examples</span></span>  
  
#### <a name="a-using-a-system-name"></a><span data-ttu-id="3e3e0-145">R.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-145">A.</span></span> <span data-ttu-id="3e3e0-146">Utilisation d'un nom système</span><span class="sxs-lookup"><span data-stu-id="3e3e0-146">Using a system name</span></span>  
 <span data-ttu-id="3e3e0-147">L'URL de point de terminaison suivante spécifie un nom système, `SYSTEM46`, et le port `7022`.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-147">The following endpoint URL specifies a system name, `SYSTEM46`, and port `7022`.</span></span>  
  
 `TCP://SYSTEM46:7022`  
  
#### <a name="b-using-a-fully-qualified-domain-name"></a><span data-ttu-id="3e3e0-148">B.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-148">B.</span></span> <span data-ttu-id="3e3e0-149">Utilisation d'un nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="3e3e0-149">Using a fully qualified domain name</span></span>  
 <span data-ttu-id="3e3e0-150">L'URL de point de terminaison suivante spécifie un nom de domaine complet, `DBSERVER8.manufacturing.Adventure-Works.com`, et le port `7024`.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-150">The following endpoint URL specifies a fully qualified domain name, `DBSERVER8.manufacturing.Adventure-Works.com`, and port `7024`.</span></span>  
  
 `TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024`  
  
#### <a name="c-using-ipv4"></a><span data-ttu-id="3e3e0-151">C.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-151">C.</span></span> <span data-ttu-id="3e3e0-152">Utilisation d'une adresse IPv4</span><span class="sxs-lookup"><span data-stu-id="3e3e0-152">Using IPv4</span></span>  
 <span data-ttu-id="3e3e0-153">L'URL de point de terminaison suivante spécifie une adresse IPv4, `10.193.9.134`, et le port `7023`.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-153">The following endpoint URL specifies an IPv4 address, `10.193.9.134`, and port `7023`.</span></span>  
  
 `TCP://10.193.9.134:7023`  
  
#### <a name="d-using-ipv6"></a><span data-ttu-id="3e3e0-154">D.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-154">D.</span></span> <span data-ttu-id="3e3e0-155">Utilisation d'une adresse IPv6</span><span class="sxs-lookup"><span data-stu-id="3e3e0-155">Using IPv6</span></span>  
 <span data-ttu-id="3e3e0-156">L'URL de point de terminaison suivante contient une adresse IPv6, `2001:4898:23:1002:20f:1fff:feff:b3a3`, et le port `7022`.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-156">The following endpoint URL contains an IPv6 address, `2001:4898:23:1002:20f:1fff:feff:b3a3`, and port `7022`.</span></span>  
  
 `TCP://[2001:4898:23:1002:20f:1fff:feff:b3a3]:7022`  
  
##  <a name="finding-the-fully-qualified-domain-name-of-a-system"></a><a name="Finding_FQDN"></a> <span data-ttu-id="3e3e0-157">Recherche du nom de domaine complet d'un système</span><span class="sxs-lookup"><span data-stu-id="3e3e0-157">Finding the Fully Qualified Domain Name of A System</span></span>  
 <span data-ttu-id="3e3e0-158">Pour rechercher le nom de domaine complet d'un système, à l'invite de commandes Windows de ce système, entrez :</span><span class="sxs-lookup"><span data-stu-id="3e3e0-158">To find the fully qualified domain name of a system, at the Windows command prompt on that system, enter:</span></span>  
  
 <span data-ttu-id="3e3e0-159">**IPCONFIG /ALL**</span><span class="sxs-lookup"><span data-stu-id="3e3e0-159">**IPCONFIG /ALL**</span></span>  
  
 <span data-ttu-id="3e3e0-160">Pour former le nom de domaine complet, concaténez les valeurs de *<host_name>* et *<Primary_Dns_Suffix>* de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="3e3e0-160">To form the fully qualified domain name, concatenate the values of *<host_name>* and *<Primary_Dns_Suffix>* as follows:</span></span>  
  
 <span data-ttu-id="3e3e0-161">_<host_name>_ **.**</span><span class="sxs-lookup"><span data-stu-id="3e3e0-161">_<host_name>_ **.**</span></span> <span data-ttu-id="3e3e0-162">_<Suffixe_DNS_principal>_</span><span class="sxs-lookup"><span data-stu-id="3e3e0-162">_<Primary_Dns_Suffix>_</span></span>  
  
 <span data-ttu-id="3e3e0-163">Par exemple, la configuration IP</span><span class="sxs-lookup"><span data-stu-id="3e3e0-163">For example, the IP configuration</span></span>  
  
 `Host Name  .  .  .  .  .  .  : MYSERVER`  
  
 `Primary Dns Suffix  .  .  .  : mydomain.Adventure-Works.com`  
  
 <span data-ttu-id="3e3e0-164">équivaut au nom de domaine complet suivant :</span><span class="sxs-lookup"><span data-stu-id="3e3e0-164">equates to the following fully qualified domain name:</span></span>  
  
 `MYSERVER.mydomain.Adventure-Works.com`  
  
> [!NOTE]  
>  <span data-ttu-id="3e3e0-165">Pour obtenir des informations supplémentaires sur un nom de domaine complet, contactez votre administrateur système.</span><span class="sxs-lookup"><span data-stu-id="3e3e0-165">If you need more information about a fully qualified domain name, see your system administrator.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3e3e0-166">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="3e3e0-166">Related Tasks</span></span>  
 <span data-ttu-id="3e3e0-167">**Pour configurer un point de terminaison de mise en miroir de bases de données**</span><span class="sxs-lookup"><span data-stu-id="3e3e0-167">**To Configure a Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="3e3e0-168">Créer un point de terminaison de mise en miroir de bases de données pour groupes de disponibilité AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="3e3e0-168">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="3e3e0-169">Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e3e0-169">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="3e3e0-170">Utiliser des certificats pour un point de terminaison de mise en miroir de bases de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e3e0-170">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="3e3e0-171">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e3e0-171">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="3e3e0-172">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions entrantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e3e0-172">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="3e3e0-173">Spécifier une adresse réseau de serveur &#40;mise en miroir de bases de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3e3e0-173">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="3e3e0-174">Résoudre les problèmes de configuration de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;supprimé</span><span class="sxs-lookup"><span data-stu-id="3e3e0-174">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
 <span data-ttu-id="3e3e0-175">**Pour afficher des informations sur le point de terminaison de mise en miroir de bases de données**</span><span class="sxs-lookup"><span data-stu-id="3e3e0-175">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="3e3e0-176">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e3e0-176">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
 <span data-ttu-id="3e3e0-177">**Pour ajouter un réplica de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="3e3e0-177">**To add an availability replica**</span></span>  
  
-   [<span data-ttu-id="3e3e0-178">Ajouter un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e3e0-178">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="3e3e0-179">Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e3e0-179">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="3e3e0-180">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="3e3e0-180">Related Content</span></span>  
  
-   [<span data-ttu-id="3e3e0-181">Guide de solutions Microsoft SQL Server AlwaysOn pour la haute disponibilité et la récupération d'urgence</span><span class="sxs-lookup"><span data-stu-id="3e3e0-181">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
## <a name="see-also"></a><span data-ttu-id="3e3e0-182">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e3e0-182">See Also</span></span>  
 <span data-ttu-id="3e3e0-183">[Création et configuration des groupes de disponibilité &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3e3e0-183">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="3e3e0-184">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3e3e0-184">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="3e3e0-185">CREATE ENDPOINT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e3e0-185">CREATE ENDPOINT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-endpoint-transact-sql)  
