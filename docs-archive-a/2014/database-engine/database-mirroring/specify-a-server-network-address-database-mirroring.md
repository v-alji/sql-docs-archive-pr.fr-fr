---
title: Spécifier une adresse réseau de serveur (mise en miroir de bases de données) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- database mirroring [SQL Server], endpoint
- endpoints [SQL Server], database mirroring
- server network addresses [SQL Server]
ms.assetid: a64d4b6b-9016-4f1e-a310-b1df181dd0c6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5c7db7ee6d321229205248059ce09a86f1da101f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610835"
---
# <a name="specify-a-server-network-address-database-mirroring"></a><span data-ttu-id="63f03-102">Spécifier une adresse réseau de serveur (mise en miroir de bases de données)</span><span class="sxs-lookup"><span data-stu-id="63f03-102">Specify a Server Network Address (Database Mirroring)</span></span>
  <span data-ttu-id="63f03-103">La configuration d'une session de mise en miroir de bases de données requiert une adresse réseau de serveur pour chaque instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="63f03-103">Setting up a database mirroring session requires a server network address for each of the server instances.</span></span> <span data-ttu-id="63f03-104">L'adresse réseau de serveur d'une instance de serveur doit identifier sans ambiguïté l'instance en fournissant une adresse système et le numéro du port sur lequel l'instance est à l'écoute.</span><span class="sxs-lookup"><span data-stu-id="63f03-104">The server network address of a server instance must unambiguously identify the instance by providing a system address and the number of the port on which the instance is listening.</span></span>  
  
 <span data-ttu-id="63f03-105">Avant de pouvoir spécifier un port dans une adresse réseau de serveur, le point de terminaison de mise en miroir de bases de données doit exister sur l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="63f03-105">Before you can specify a port in a server network address, the database mirroring endpoint must exist on the server instance.</span></span> <span data-ttu-id="63f03-106">Pour plus d’informations, consultez [Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="63f03-106">For more information, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
  
  
##  <a name="syntax-for-a-server-network-address"></a><a name="Syntax"></a> <span data-ttu-id="63f03-107">Syntaxe d'une adresse réseau de serveur</span><span class="sxs-lookup"><span data-stu-id="63f03-107">Syntax for a Server Network Address</span></span>  
 <span data-ttu-id="63f03-108">La syntaxe d'une adresse réseau de serveur est de la forme :</span><span class="sxs-lookup"><span data-stu-id="63f03-108">The syntax for a server network address is of the form:</span></span>  
  
 <span data-ttu-id="63f03-109">TCP<strong>://</strong> *\<system-address>* <strong> :<strong>*\<port>*</span><span class="sxs-lookup"><span data-stu-id="63f03-109">TCP<strong>://</strong>*\<system-address>*<strong>:<strong>*\<port>*</span></span> 
  
 <span data-ttu-id="63f03-110">where</span><span class="sxs-lookup"><span data-stu-id="63f03-110">where</span></span>  
  
-   <span data-ttu-id="63f03-111">*\<system-address>* est une chaîne qui identifie sans ambiguïté le système informatique de destination.</span><span class="sxs-lookup"><span data-stu-id="63f03-111">*\<system-address>* is a string that unambiguously identifies the destination computer system.</span></span> <span data-ttu-id="63f03-112">En règle générale, l'adresse de serveur est un nom système (si les systèmes sont dans le même domaine), un nom de domaine complet ou une adresse IP :</span><span class="sxs-lookup"><span data-stu-id="63f03-112">Typically, the server address is a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address:</span></span>  
  
    -   <span data-ttu-id="63f03-113">Si les systèmes sont dans le même domaine, vous pouvez utiliser le nom du système informatique ; par exemple, `SYSTEM46`.</span><span class="sxs-lookup"><span data-stu-id="63f03-113">If the systems are the same domain, you can use the name of the computer system; for example, `SYSTEM46`.</span></span>  
  
    -   <span data-ttu-id="63f03-114">Pour pouvoir utiliser une adresse IP, elle doit être unique dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="63f03-114">To use an IP address, it must be unique in your environment.</span></span> <span data-ttu-id="63f03-115">Nous vous recommandons d'utiliser une adresse IP seulement si elle est statique.</span><span class="sxs-lookup"><span data-stu-id="63f03-115">We recommend that you use an IP address only if it is static.</span></span> <span data-ttu-id="63f03-116">L'adresse IP peut être une adresse IP Version 4 (IPv4) ou IP Version 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="63f03-116">The IP address can be IP Version 4 (IPv4) or IP Version 6 (IPv6).</span></span> <span data-ttu-id="63f03-117">Une adresse IPv6 doit être placée entre crochets, par exemple : **[** _<adresse_IPv6>_ **]** .</span><span class="sxs-lookup"><span data-stu-id="63f03-117">An IPv6 address must be enclosed within square brackets, for example: **[**_<IPv6_address>_**]**.</span></span>  
  
         <span data-ttu-id="63f03-118">Pour connaître l'adresse IP d'un système, à l'invite de commandes Windows, entrez la commande **ipconfig** .</span><span class="sxs-lookup"><span data-stu-id="63f03-118">To learn the IP address of a system, at the Windows command prompt, enter the **ipconfig** command.</span></span>  
  
    -   <span data-ttu-id="63f03-119">L'utilisation du nom de domaine complet garantit un fonctionnement correct.</span><span class="sxs-lookup"><span data-stu-id="63f03-119">The fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="63f03-120">Il s'agit d'une chaîne d'adresse définie localement qui présente des formes différentes dans des emplacements différents.</span><span class="sxs-lookup"><span data-stu-id="63f03-120">This is a locally defined address string that different forms in different places.</span></span> <span data-ttu-id="63f03-121">Souvent, mais pas systématiquement, un nom de domaine complet correspond à un nom composé qui inclut le nom de l'ordinateur et une série de segments de domaine séparés par des points, de la forme :</span><span class="sxs-lookup"><span data-stu-id="63f03-121">Often, but not always, a fully qualified domain name is a compound name that includes the computer name and a series of period-separated domain segments of the form:</span></span>  
  
         <span data-ttu-id="63f03-122">_nom_ordinateur_ **.**</span><span class="sxs-lookup"><span data-stu-id="63f03-122">_computer_name_ **.**</span></span> <span data-ttu-id="63f03-123">_segment_domaine_[... **.** _segment_domaine_]</span><span class="sxs-lookup"><span data-stu-id="63f03-123">_domain_segment_[...**.**_domain_segment_]</span></span>  
  
         <span data-ttu-id="63f03-124">où *nom_ordinateur*correspond au nom réseau de l’ordinateur qui exécute l’instance de serveur et *segment_domaine*[... **.** _segment_domaine_] représente les autres informations de domaine du serveur ; par exemple : `localinfo.corp.Adventure-Works.com`.</span><span class="sxs-lookup"><span data-stu-id="63f03-124">where *computer_name i*s the network name of the computer running the server instance, and *domain_segment*[...**.**_domain_segment_] is the remaining domain information of the server; for example: `localinfo.corp.Adventure-Works.com`.</span></span>  
  
         <span data-ttu-id="63f03-125">Le contenu et le nombre de segments de domaine sont déterminés au sein de la société ou de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="63f03-125">The content and number of domain segments are determined within the company or organization.</span></span> <span data-ttu-id="63f03-126">Si vous ne connaissez pas le nom de domaine complet de votre serveur, contactez votre administrateur système.</span><span class="sxs-lookup"><span data-stu-id="63f03-126">If you do not know the fully qualified domain name for your server, see your system administrator.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="63f03-127">Pour plus d'informations sur la recherche d'un nom de domaine complet, consultez « Recherche du nom de domaine complet » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="63f03-127">For information about how to find a fully qualified domain name, see "Finding the Fully Qualified Domain Name," later in this topic.</span></span>  
  
-   <span data-ttu-id="63f03-128">*\<port>* est le numéro de port utilisé par le point de terminaison de mise en miroir de l'instance de serveur partenaire.</span><span class="sxs-lookup"><span data-stu-id="63f03-128">*\<port>* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="63f03-129">Pour plus d’informations sur la spécification d’un point de terminaison, consultez [Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="63f03-129">For information about specifying an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
     <span data-ttu-id="63f03-130">Un point de terminaison de mise en miroir de bases de données peut utiliser tout port disponible sur le système informatique.</span><span class="sxs-lookup"><span data-stu-id="63f03-130">A database mirroring endpoint can use any available port on the computer system.</span></span> <span data-ttu-id="63f03-131">Chaque numéro de port sur un système d'ordinateur doit être associé à un seul point de terminaison, et chaque point de terminaison est associé à une seule instance de serveur ; ainsi, différentes instances de serveurs sur le même serveur écoutent sur différents points de terminaison dotés de différents ports.</span><span class="sxs-lookup"><span data-stu-id="63f03-131">Each port number on a computer system must be associated with only one endpoint, and each endpoint is associated with a single server instance; thus, different server instances on the same server listen on different endpoints with different ports.</span></span> <span data-ttu-id="63f03-132">Par conséquent, le port que vous spécifiez dans l'adresse réseau du serveur lorsque vous configurez une session de mise en miroir de bases de données dirigera systématiquement la session vers l'instance de serveur dont le point de terminaison est associé à ce port.</span><span class="sxs-lookup"><span data-stu-id="63f03-132">Therefore, the port you specify in the server network address when you set up a database mirroring session will always direct the session to the server instance whose endpoint is associated with that port.</span></span>  
  
     <span data-ttu-id="63f03-133">Dans l'adresse réseau d'une instance de serveur, seul le numéro de port associé à son point de terminaison de mise en miroir permet de différencier cette instance des autres instances sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="63f03-133">In the server network address of a server instance, only the number of the port associated with its mirroring endpoint distinguishes that instance from any other instances on the computer.</span></span> <span data-ttu-id="63f03-134">L'illustration suivante présente les adresses réseau de deux instances de serveurs sur un même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="63f03-134">The following figure illustrates the server network addresses of two server instances on a single computer.</span></span> <span data-ttu-id="63f03-135">L'instance par défaut utilise le port `7022` et l'instance nommée utilise le port `7033`.</span><span class="sxs-lookup"><span data-stu-id="63f03-135">The default instance uses port `7022` and the named instance uses port `7033`.</span></span> <span data-ttu-id="63f03-136">Les adresses réseau de serveur de ces deux instances de serveur sont, respectivement : `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` et `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span><span class="sxs-lookup"><span data-stu-id="63f03-136">The server network address for these two server instances are, respectively: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` and `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span></span> <span data-ttu-id="63f03-137">Notez que l'adresse ne contient pas le nom de l'instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="63f03-137">Note that the address does not contain the name of the server instance.</span></span>  
  
     <span data-ttu-id="63f03-138">![Adresses réseau de serveur d’une instance par défaut](../media/dbm-2-instances-ports-1-system.gif "Adresses réseau de serveur d’une instance par défaut")</span><span class="sxs-lookup"><span data-stu-id="63f03-138">![Server network addresses of a default instance](../media/dbm-2-instances-ports-1-system.gif "Server network addresses of a default instance")</span></span>  
  
     <span data-ttu-id="63f03-139">Pour identifier le port actuellement associé au point de terminaison de mise en miroir de bases de données d'une instance de serveur, utilisez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante :</span><span class="sxs-lookup"><span data-stu-id="63f03-139">To identify the port currently associated with database mirroring endpoint of a server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT type_desc, port FROM sys.tcp_endpoints  
    ```  
  
     <span data-ttu-id="63f03-140">Recherchez la ligne dont la valeur **type_desc** est « DATABASE_MIRRORING » et utilisez le numéro de port correspondant.</span><span class="sxs-lookup"><span data-stu-id="63f03-140">Find the row whose **type_desc** value is "DATABASE_MIRRORING," and use the corresponding port number.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="63f03-141">Exemples</span><span class="sxs-lookup"><span data-stu-id="63f03-141">Examples</span></span>  
  
#### <a name="a-using-a-system-name"></a><span data-ttu-id="63f03-142">R.</span><span class="sxs-lookup"><span data-stu-id="63f03-142">A.</span></span> <span data-ttu-id="63f03-143">Utilisation d'un nom système</span><span class="sxs-lookup"><span data-stu-id="63f03-143">Using a system name</span></span>  
 <span data-ttu-id="63f03-144">L'adresse réseau de serveur suivante spécifie un nom système, `SYSTEM46`, et un port, `7022`.</span><span class="sxs-lookup"><span data-stu-id="63f03-144">The following server network address specifies a system name, `SYSTEM46`, and port `7022`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://SYSTEM46:7022';  
```  
  
#### <a name="b-using-a-fully-qualified-domain-name"></a><span data-ttu-id="63f03-145">B.</span><span class="sxs-lookup"><span data-stu-id="63f03-145">B.</span></span> <span data-ttu-id="63f03-146">Utilisation d'un nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="63f03-146">Using a fully qualified domain name</span></span>  
 <span data-ttu-id="63f03-147">L'adresse réseau de serveur suivante spécifie un nom de domaine complet, `DBSERVER8.manufacturing.Adventure-Works.com`, et un port, `7024`.</span><span class="sxs-lookup"><span data-stu-id="63f03-147">The following server network address specifies a fully qualified domain name, `DBSERVER8.manufacturing.Adventure-Works.com`, and port `7024`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://DBSERVER8.manufacturing.Adventure-Works.com:7024';  
```  
  
#### <a name="c-using-ipv4"></a><span data-ttu-id="63f03-148">C.</span><span class="sxs-lookup"><span data-stu-id="63f03-148">C.</span></span> <span data-ttu-id="63f03-149">Utilisation d'une adresse IPv4</span><span class="sxs-lookup"><span data-stu-id="63f03-149">Using IPv4</span></span>  
 <span data-ttu-id="63f03-150">L'adresse réseau de serveur suivante spécifie une adresse IPv4, `10.193.9.134`, et un port, `7023`.</span><span class="sxs-lookup"><span data-stu-id="63f03-150">The following server network address specifies an IPv4 address, `10.193.9.134`, and port `7023`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://10.193.9.134:7023';  
```  
  
#### <a name="d-using-ipv6"></a><span data-ttu-id="63f03-151">D.</span><span class="sxs-lookup"><span data-stu-id="63f03-151">D.</span></span> <span data-ttu-id="63f03-152">Utilisation d'une adresse IPv6</span><span class="sxs-lookup"><span data-stu-id="63f03-152">Using IPv6</span></span>  
 <span data-ttu-id="63f03-153">L'adresse réseau de serveur suivante contient une adresse IPv6, `2001:4898:23:1002:20f:1fff:feff:b3a3`, et un port, `7022`.</span><span class="sxs-lookup"><span data-stu-id="63f03-153">The following server network address contains an IPv6 address, `2001:4898:23:1002:20f:1fff:feff:b3a3`, and port `7022`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://[2001:4898:23:1002:20f:1fff:feff:b3a3]:7022';  
```  
  
## <a name="finding-the-fully-qualified-domain-name"></a><span data-ttu-id="63f03-154">Recherche du nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="63f03-154">Finding the Fully Qualified Domain Name</span></span>  
 <span data-ttu-id="63f03-155">Pour rechercher le nom de domaine complet d'un système, à l'invite de commandes Windows de ce système, entrez :</span><span class="sxs-lookup"><span data-stu-id="63f03-155">To find the fully qualified domain name of a system, at the Windows command prompt on that system, enter:</span></span>  
  
 <span data-ttu-id="63f03-156">**IPCONFIG /ALL**</span><span class="sxs-lookup"><span data-stu-id="63f03-156">**IPCONFIG /ALL**</span></span>  
  
 <span data-ttu-id="63f03-157">Pour former le nom de domaine complet, concaténez les valeurs de *<host_name>* et *<Primary_Dns_Suffix>* de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="63f03-157">To form the fully qualified domain name, concatenate the values of *<host_name>* and *<Primary_Dns_Suffix>* as follows:</span></span>  
  
 <span data-ttu-id="63f03-158">_<host_name>_ **.**</span><span class="sxs-lookup"><span data-stu-id="63f03-158">_<host_name>_ **.**</span></span> <span data-ttu-id="63f03-159">_<Suffixe_DNS_principal>_</span><span class="sxs-lookup"><span data-stu-id="63f03-159">_<Primary_Dns_Suffix>_</span></span>  
  
 <span data-ttu-id="63f03-160">Par exemple, la configuration IP</span><span class="sxs-lookup"><span data-stu-id="63f03-160">For example, the IP configuration</span></span>  
  
 `Host Name  .  .  .  .  .  .  : MYSERVER`  
  
 `Primary Dns Suffix  .  .  .  : mydomain.Adventure-Works.com`  
  
 <span data-ttu-id="63f03-161">équivaut au nom de domaine complet suivant :</span><span class="sxs-lookup"><span data-stu-id="63f03-161">equates to the following fully qualified domain name:</span></span>  
  
 `MYSERVER.mydomain.Adventure-Works.com`  
  
##  <a name="examples"></a><a name="Examples"></a> <span data-ttu-id="63f03-162">Exemples</span><span class="sxs-lookup"><span data-stu-id="63f03-162">Examples</span></span>  
 <span data-ttu-id="63f03-163">L'exemple suivant montre l'adresse réseau de serveur d'une instance de serveur sur un système informatique nommé `REMOTESYSTEM3` dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="63f03-163">The following example shows the server network address for a server instance on a computer system named `REMOTESYSTEM3` in another domain.</span></span> <span data-ttu-id="63f03-164">Les informations du domaine sont `NORTHWEST.ADVENTURE-WORKS.COM`et le port du point de terminaison de mise en miroir de bases de données est `7025`.</span><span class="sxs-lookup"><span data-stu-id="63f03-164">The domain information is `NORTHWEST.ADVENTURE-WORKS.COM`, and the port of the database mirroring endpoint is `7025`.</span></span> <span data-ttu-id="63f03-165">Étant donné ces exemples de composants, l'adresse réseau du serveur est la suivante :</span><span class="sxs-lookup"><span data-stu-id="63f03-165">Given these example components, the server network address is.</span></span>  
  
 `TCP://REMOTESYSTEM3.NORTHWEST.ADVENTURE-WORKS.COM:7025`  
  
 <span data-ttu-id="63f03-166">L'exemple suivant montre l'adresse réseau de serveur d'une instance de serveur sur un système informatique nommé `DBSERVER1`.</span><span class="sxs-lookup"><span data-stu-id="63f03-166">The following example shows the server network address for a server instance on a computer system named `DBSERVER1`.</span></span> <span data-ttu-id="63f03-167">Ce système se trouve dans le domaine local et il est identifié sans ambiguïté par son nom système.</span><span class="sxs-lookup"><span data-stu-id="63f03-167">This system is in the local domain and is unambiguously identified by its system name.</span></span> <span data-ttu-id="63f03-168">Le port du point de terminaison de mise en miroir de bases de données est `7022`.</span><span class="sxs-lookup"><span data-stu-id="63f03-168">The port of the database mirroring endpoint is `7022`.</span></span>  
  
 `TCP://DBSERVER1:7022`  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="63f03-169">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="63f03-169">Related Tasks</span></span>  
  
-   [<span data-ttu-id="63f03-170">Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="63f03-170">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="63f03-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="63f03-171">See Also</span></span>  
 <span data-ttu-id="63f03-172">[Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="63f03-172">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="63f03-173">Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="63f03-173">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
  
  
