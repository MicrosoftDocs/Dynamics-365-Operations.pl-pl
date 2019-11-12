---
title: Zintegrowane witryny i magazyny
description: W tym temacie opisano integrację danych witryny i magazyny między programami Finance and Operations i Common Data Service.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 093f33e313bfb194ef932dffe9c9b5bcb84ae762
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569232"
---
# <a name="integrated-sites-and-warehouses"></a>Zintegrowane witryny i magazyny

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

W tym temacie opisano integrację danych witryny i magazyny między programami Finance and Operations i Common Data Service. Lokacje i magazyny operacyjne są typowymi pojęciami w aplikacji Supply Chain Management. Służą one do modelowania łańcucha dostaw firmy.

## <a name="templates"></a>Szablony

Dzięki integracji z Common Data Service, te pojęcia i wszystkie informacje związane z nimi są dostępne w Common Data Service przy użyciu stron i magazynów wymienionych w poniższej tabeli.

Aplikacje Finance and Operations | Inne aplikacje w usłudze Dynamics 365
--------------------------|---------------------------------
Oddziały                     | msdyn_operationalsites
Magazyny                | magazyny

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="operational-sites"></a>Lokacje operacyjne

Lokacje operacyjne są dostępne w Common Data Service przy użyciu następujących mapowań.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
SITENAME | >< | msdyn_name
DEFAULTFINANCIALDIMENSIONVALUE | >< | msdyn_defaultfinancialdimensionvalue
DEFAULTINVENTORYSTATUSID | >< | msdyn_defaultinventorystatusid
ISRECEIVINGWAREHOUSEOVERRIDEALLOWED | >< | msdyn_isreceivingwarehouseoverrideallowed
SITEID | >< | msdyn_siteid
SITENAME | >< | msdyn_sitename
TAXBRANCHCODE | >< | msdyn_taxbranchcode
FISCALESTABLISHMENTID | >< | msdyn_fiscalestablishmentid
ISPRIMARYADDRESSASSIGNED | >< | msdyn_isprimaryaddressassigned
PRIMARYADDRESSCITY | >< | msdyn_primaryaddresscity
PRIMARYADDRESSCOUNTRYREGIONID | >< | msdyn_primaryaddresscountryregionid
PRIMARYADDRESSCOUNTYID | >< | msdyn_primaryaddresscountyid
PRIMARYADDRESSDISTRICTNAME | >< | msdyn_primaryaddressdistrictname
PRIMARYADDRESSLATITUDE | >< | msdyn_primaryaddresslatitude
PRIMARYADDRESSLOCATIONROLES | >< | msdyn_primaryaddresslocationrole
PRIMARYADDRESSLOCATIONSALESTAXGROUPCODE | >< | msdyn_primaryaddresslocationsalestaxgroupcode
PRIMARYADDRESSLONGITUDE | >< | msdyn_primaryaddresslongitude
PRIMARYADDRESSSTATEID | >< | msdyn_primaryaddressstateid
PRIMARYADDRESSSTREET | >< | msdyn_primaryaddressstreet
PRIMARYADDRESSZIPCODE | >< | msdyn_primaryaddresszipcode
PRIMARYADDRESSBUILDINGCOMPLIMENT | >< | msdyn_primaryaddressbuildingcompliment
PRIMARYADDRESSCITYINKANA | >< | msdyn_primaryaddresscityinkana
PRIMARYADDRESSSTREETINKANA | >< | msdyn_primaryaddressstreetinkana
PRIMARYADDRESSDESCRIPTION | >< | msdyn_primaryaddressdescription
FORMATTEDPRIMARYADDRESS | >< | msdyn_formattedprimaryaddress
WILLMASTERPLANNEDINTRASITEMOVEMENTSUSETRANSFERJOURNALS | >< | msdyn_masterplannedusestransferjournal
PRIMARYADDRESSPOSTBOX | >< | msdyn_primaryaddresspostbox
PRIMARYADDRESSSTREETNUMBER | >< | msdyn_primaryaddressstreetnumber


## <a name="warehouses"></a>Magazyny

Magazyny są dostępne w przy użyciu następujących mapowań.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
DEFAULTCONTAINERTYPEID | >> | msdyn_defaultcontainertypeid
AREITEMSCOVERAGEPLANNEDMANUALLY | >> | msdyn_areitemscoverageplannedmanually
ARELABORSTANDARDSALLOWED | >> | msdyn_arelaborstandardsallowed
PRIMARYADDRESSBUILDINGCOMPLIMENT | >> | msdyn_primaryaddressbuildingcompliment
PRIMARYADDRESSPOSTBOX | >> | msdyn_primaryaddresspostbox
PRIMARYADDRESSSTREETNUMBER | >> | msdyn_primaryaddressstreetnumber
AREWAREHOUSELOCATIONCHECKDIGITSUNIQUE | >> | msdyn_arewarehouselocationcheckdigitsunique
INVENTORYCOUNTINGREASONCODEPOLICYNAME | >> | msdyn_inventorycountingreasoncodepolicyname
AUTOUPDATESHIPMENTRULE | >> | msdyn_autoupdateshipmentrule
WAREHOUSERELEASERESERVATIONREQUIREMENTRULE | >> | msdyn_warehousereleasereservationrequirement
EXTERNALLYLOCATEDWAREHOUSEVENDORACCOUNTNUMBER | >> | msdyn_externallylocatedwarehousevendoraccountnu
INVENTORYSTATUSCHANGERESERVATIONREMOVALLEVEL | >> | msdyn_inventorystatuschangereservationremoval
WAREHOUSEWORKPROCESSINGPOLICYNAME | >> | msdyn_warehouseworkprocessingpolicyname
ISFALLBACKWAREHOUSE | >> | msdyn_isfallbackwarehouse
ISFINANCIALNEGATIVERETAILSTOREINVENTORYALLOWED | >> | msdyn_financialnegativestoreinventoryallowed
ISPALLETMOVEMENTDURINGCYCLECOUNTINGALLOWED | >> | msdyn_palletmovementduringcyclecountingallowed
ISPHYSICALNEGATIVERETAILSTOREINVENTORYALLOWED | >> | msdyn_physicalnegativestoreinventoryallowed
ISREFILLEDFROMMAINWAREHOUSE | >> | msdyn_isrefilledfrommainwarehouse
ISRETAILSTOREWAREHOUSE | >> | msdyn_isretailstorewarehouse
MAINREFILLINGWAREHOUSEID | >> | msdyn_mainrefillingwarehouseid.msdyn_warehouseid
MASTERPLANNINGWORKCALENDARDID | >> | msdyn_masterplanningworkcalendarid
MAXIMUMBATCHPICKINGLISTQUANTITY | >> | msdyn_maximumbatchpickinglistquantity
MAXIMUMPICKINGLISTLINEQUANTITY | >> | msdyn_maximumpickinglistlinequantity
OPERATIONALSITEID | >> | msdyn_operationalsiteid.msdyn_siteid
QUARANTINEWAREHOUSEID | >> | msdyn_quarantinewarehouseid.msdyn_warehouseid
RETAILSTOREQUANTITYALLOCATIONREPLENISMENTRULEWEIGHT | > | msdyn_storeqtyallocationreplenishmentweight
SHOULDWAREHOUSELOCATIONIDINCLUDEAISLEID | >> | msdyn_shouldwarehouselocationincludeaisleid
TRANSITWAREHOUSEID | >> | msdyn_transitwarehouseid.msdyn_warehouseid
WAREHOUSEID | >> | msdyn_warehouseid
WAREHOUSELOCATIONIDBINIDFORMAT | >> | msdyn_warehouselocationidbinidformat
WAREHOUSELOCATIONIDRACKIDFORMAT | >> | msdyn_warehouselocationidrackidformat
WAREHOUSELOCATIONIDSHELFIDFORMAT | >> | msdyn_warehouselocationidshelfidformat
WAREHOUSENAME | >> | msdyn_name
WAREHOUSENAME | >> | msdyn_warehousename
WAREHOUSESPECIFICDEFAULTINVENTORYSTATUSID | >> | msdyn_warehousespecificdefaultinventorystatusid
WAREHOUSETYPE | >> | msdyn_warehousetype
ISPRIMARYADDRESSASSIGNED | >> | msdyn_isprimaryaddressassigned
PRIMARYADDRESSCITY | >> | msdyn_primaryaddresscity
PRIMARYADDRESSCOUNTRYREGIONID | >> | msdyn_primaryaddresscountryregionid
PRIMARYADDRESSCOUNTYID | >> | msdyn_primaryaddresscountyid
PRIMARYADDRESSDISTRICTNAME | >> | msdyn_primaryaddressdistrictname
PRIMARYADDRESSLATITUDE | >> | msdyn_primaryaddresslatitude
PRIMARYADDRESSLONGITUDE | >> | msdyn_primaryaddresslongitude
PRIMARYADDRESSLOCATIONROLES | >> | msdyn_primaryaddresslocationroles
PRIMARYADDRESSLOCATIONSALESTAXGROUPCODE | >> | msdyn_primaryaddresslocationsalestaxgroupcode
PRIMARYADDRESSSTATEID | >> | msdyn_primaryaddressstateid
PRIMARYADDRESSSTREET | >> | msdyn_primaryaddressstreet
PRIMARYADDRESSZIPCODE | >> | msdyn_primaryaddresszipcode
EXTERNALLYLOCATEDWAREHOUSECUSTOMERACCOUNTNUMBER | >> | msdyn_externallylocatedwarehousecustomeraccount
PRIMARYADDRESSCITYINKANA | >> | msdyn_primaryaddresscityinkana
PRIMARYADDRESSSTREETINKANA | >> | msdyn_primaryaddressstreetinkana
PRIMARYADDRESSDESCRIPTION | >> | msdyn_primaryaddressdescription
AREADVANCEDWAREHOUSEMANAGEMENTPROCESSESENABLED | >> | msdyn_uesadvancedwarehousemanagementprocesses
AREPICKINGLISTSDELIVERYMODESPECIFIC | >> | msdyn_arepickinglistsdeliverymodespecific
AREPICKINGLISTSSHIPMENTSPECIFICONLY | >> | msdyn_arepickinglistshipmentspecificonly
FORMATTEDPRIMARYADDRESS | >> | msdyn_formattedprimaryaddress
ISBILLOFLADINGPRINTINGBEFORESHIPMENTCONFIRMATIONENABLED | >> | msdyn_printbillofladingbeforeshipconfirmation
RAWMATERIALPICKINGINVENTORYISSUESTATUS | >> | msdyn_rawmaterialpickinginventoryissuestatus
WILLAUTOMATICLOADRELEASERESERVEINVENTORY | >> | msdyn_willautomaticloadreleaseinventory
WILLINVENTORYSTATUSCHANGEREMOVEBLOCKING | >> | msdyn_willinventorystatuschangeremoveblocking
WILLMANUALLOADRELEASERESERVEINVENTORY | >> | msdyn_willmanualloadreleasereserveinventory
WILLORDERRELEASINGCONSOLIDATESHIPMENTS | >> | msdyn_willorderreleasingconsolidateshipments
WILLPRODUCTIONBOMSRESERVEWAREHOUSELEVELONLY | >> | msdyn_productionbomsreservewarehouselevel
WILLSHIPPINGCANCELLATIONDECREMENTLOADQUANITY | >> | msdyn_shippingcanceldecrementloadquantity
WILLWAREHOUSELOCATIONIDINCLUDEBINIDBYDEFAULT | >> | msdyn_warehouselocationidincludeblindid
WILLWAREHOUSELOCATIONIDINCLUDERACKIDBYDEFAULT | >> | msdyn_warehouselocationincluderackidbydefault
WILLWAREHOUSELOCATIONIDINCLUDESHELFIDBYDEFAULT | >> | msdyn_warehouselocationidincludeshelfid
