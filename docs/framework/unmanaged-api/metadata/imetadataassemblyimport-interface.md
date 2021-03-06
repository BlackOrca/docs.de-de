---
title: IMetaDataAssemblyImport-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da75f98edb54080658dc86f48d4ebb458d72f20d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449311"
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport-Schnittstelle
Stellt Methoden zum Zugreifen auf und Untersuchen der Inhalte eines Assemblymanifests bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CloseEnum-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|Gibt das Handle für den angegebenen Enumerator frei.|  
|[EnumAssemblyRefs-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|Ruft einen Schnittstellenzeiger auf einem Enumerator, der enthält die `mdAssemblyRef` Token der Assemblys, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.|  
|[EnumExportedTypes-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|Ruft einen Schnittstellenzeiger auf einem Enumerator, der enthält die `mdExportedType` Token von der COM-Typen, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.|  
|[EnumFiles-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|Ruft einen Schnittstellenzeiger auf einem Enumerator, der enthält die `mdFile` Token der Dateien, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.|  
|[EnumManifestResources-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|Ruft einen Schnittstellenzeiger auf einem Enumerator, der enthält die `mdManifestResource` Token, die Ressourcen, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.|  
|[FindAssembliesByName-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|Ruft ein Array von `mdAssemblyRef` Token für die Assemblys mit dem angegebenen Namen.|  
|[FindExportedTypeByName-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|Ruft eine `mdExportedType` token für den COM-Typ mit dem angegebenen Namen.|  
|[FindManifestResourceByName-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|Ruft eine `mdManifestResource` token für die Ressource mit dem angegebenen Namen.|  
|[GetAssemblyFromScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|Ruft das Token für die Assembly im aktuellen Metadatenbereich ab.|  
|[GetAssemblyProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|Ruft die eigenschafteneinstellungen der angegebenen Assembly.|  
|[GetAssemblyRefProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|Ruft die eigenschafteneinstellungen des angegebenen `mdAssemblyRef` token.|  
|[GetExportedTypeProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|Ruft die eigenschafteneinstellungen des angegebenen COM-Typs ab.|  
|[GetFileProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|Ruft die eigenschafteneinstellungen der angegebenen Datei.|  
|[GetManifestResourceProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|Ruft die eigenschafteneinstellungen für die angegebene Manifestressource ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
