---
title: Effectuer des mises à jour partielles de données FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT
- FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT
ms.assetid: d6f7661e-6c14-4d31-9541-4520ca0f82b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 696c1a6421e14568877e24f015e5094395f1051b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707599"
---
# <a name="make-partial-updates-to-filestream-data"></a><span data-ttu-id="0aac8-102">Effectuer des mises à jour partielles de données FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="0aac8-102">Make Partial Updates to FILESTREAM Data</span></span>
  <span data-ttu-id="0aac8-103">Une application utilise FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT pour appliquer des mises à jour partielles aux données BLOB FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="0aac8-103">An application uses FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT to make partial updates to FILESTREAM BLOB data.</span></span> <span data-ttu-id="0aac8-104">La fonction [DeviceIoControl](https://go.microsoft.com/fwlink/?LinkId=105527) passe cette valeur et le descripteur qui est retourné d’ [OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) au pilote FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="0aac8-104">The [DeviceIoControl](https://go.microsoft.com/fwlink/?LinkId=105527) function passes this value and the handle that is returned from [OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) to the FILESTREAM driver.</span></span> <span data-ttu-id="0aac8-105">Le pilote force ensuite une copie côté serveur des données FILESTREAM actuelles dans le fichier référencé par le descripteur.</span><span class="sxs-lookup"><span data-stu-id="0aac8-105">The driver then forces a server-side copy of the current FILESTREAM data into the file that is referenced by the handle.</span></span> <span data-ttu-id="0aac8-106">Si l'application publie la valeur FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT après l'écriture dans le descripteur, la dernière opération d'écriture persistera et les opérations d'écriture antérieures effectuées dans le descripteur seront perdues.</span><span class="sxs-lookup"><span data-stu-id="0aac8-106">If the application issues the FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT value after the handle has been written to, the last write operation persists and previous write operations that were made to the handle are lost.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0aac8-107">FILESTREAM compte sur le [protocole SMB](https://go.microsoft.com/fwlink/?LinkId=112454) pour l’accès à distance.</span><span class="sxs-lookup"><span data-stu-id="0aac8-107">FILESTREAM relies on the [SMB protocol](https://go.microsoft.com/fwlink/?LinkId=112454) for remote access.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0aac8-108">Exemple</span><span class="sxs-lookup"><span data-stu-id="0aac8-108">Example</span></span>  
 <span data-ttu-id="0aac8-109">L'exemple suivant vous indique comment utiliser la valeur `FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT` pour effectuer une mise à jour partielle d'un BLOB FILESTREAM inséré.</span><span class="sxs-lookup"><span data-stu-id="0aac8-109">The following example shows you how to use the `FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT` value to perform a partial update of an inserted FILESTREAM BLOB.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0aac8-110">Cet exemple nécessite la base de données compatible FILESTREAM et la table qui sont créées dans [Créer une base de données compatible FILESTREAM](create-a-filestream-enabled-database.md) et [Créer une table pour le stockage de données FILESTREAM](create-a-table-for-storing-filestream-data.md).</span><span class="sxs-lookup"><span data-stu-id="0aac8-110">This example requires the FILESTREAM-enabled database and table that are created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md) and [Create a Table for Storing FILESTREAM Data](create-a-table-for-storing-filestream-data.md).</span></span>  
  
 [!code-cpp[FILESTREAM#FS_CPP_FSCTL](../../snippets/tsql/SQL15/tsql/filestream/cpp/filestream.cpp#fs_cpp_fsctl)]  
  
## <a name="see-also"></a><span data-ttu-id="0aac8-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0aac8-111">See Also</span></span>  
 <span data-ttu-id="0aac8-112">[Accéder à des données FILESTREAM avec OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span><span class="sxs-lookup"><span data-stu-id="0aac8-112">[Access FILESTREAM Data with OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span></span>  
 [<span data-ttu-id="0aac8-113">Créer des applications clientes pour les données FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="0aac8-113">Create Client Applications for FILESTREAM Data</span></span>](create-client-applications-for-filestream-data.md)  
  
  
