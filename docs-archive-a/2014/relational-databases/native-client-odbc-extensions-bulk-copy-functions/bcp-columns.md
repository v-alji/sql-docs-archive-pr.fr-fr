---
title: bcp_columns | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_columns
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_columns function
ms.assetid: 5376f6fe-9508-439a-8c66-778d77f19ac3
author: rothja
ms.author: jroth
ms.openlocfilehash: 028bb80e88a29b366e3a489abae06c8b3b30cdf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698159"
---
# <a name="bcp_columns"></a>bcp_columns
  Définit le nombre total de colonnes trouvées dans le fichier utilisateur pour une utilisation avec une copie en bloc vers ou depuis [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. [bcp_setbulkmode](bcp-setbulkmode.md) peut être utilisé à la place de bcp_columns et [bcp_colfmt](bcp-colfmt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
RETCODE bcp_columns (  
HDBC   
hdbc  
,  
INT   
nColumns  
);  
  
```  
  
## <a name="arguments"></a>Arguments  
 *hdbc*  
 Handle de connexion ODBC compatible avec la copie en bloc.  
  
 *nColumns*  
 Nombre total de colonnes dans le fichier utilisateur. Même si vous vous préparez à copier en bloc des données à partir du fichier utilisateur vers une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table et que vous n’envisagez pas de copier toutes les colonnes dans le fichier utilisateur, vous devez toujours définir *nColumns* sur le nombre total de colonnes de fichier utilisateur.  
  
## <a name="returns"></a>Retours  
 SUCCEED ou FAIL.  
  
## <a name="remarks"></a>Notes  
 Cette fonction ne peut être appelée qu’une fois que [bcp_init](bcp-init.md) a été appelé avec un nom de fichier valide.  
  
 Vous devez appeler cette fonction uniquement si vous envisagez d'utiliser un format de fichier utilisateur qui diffère du format par défaut. Pour plus d’informations sur une description du format de fichier utilisateur par défaut, consultez **bcp_init**.  
  
 Après avoir appelé `bcp_columns` , vous devez appeler [bcp_colfmt](bcp-colfmt.md)pour chaque colonne dans le fichier utilisateur afin de définir complètement un format de fichier personnalisé.  
  
## <a name="see-also"></a>Voir aussi  
 [Bulk Copy Functions](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
