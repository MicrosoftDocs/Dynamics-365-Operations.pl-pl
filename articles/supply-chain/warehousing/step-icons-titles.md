---
title: Przypisanie ikon i tytułów kroków dla aplikacji mobilnej Warehouse Management
description: W tym artykule opisano sposób przypisywania ikon kroków i tytułów dla nowych lub dostosowanych przepływów zadań w aplikacji mobilnej Warehouse Management.
author: Mirzaab
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 2ed2baff1851eba488233c050cef1f8f73b6bcee
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067311"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a>Przypisanie ikon i tytułów kroków dla aplikacji mobilnej Warehouse Management

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób przypisywania ikon kroków i tytułów kroków dla nowych lub dostosowanych przepływów zadań w aplikacji mobilnej Warehouse Management.

Na ilustracjach pokazano, jak ikony kroku i tytuły kroku pojawiają się w aplikacji mobilnej Warehouse Management.

![Przykład ikony kroku i tytułu kroku w aplikacji mobilnej Warehouse Management.](media/step-icon-example.png "Przykład ikony kroku i tytułu kroku w aplikacji mobilnej Warehouse Management")

## <a name="turn-this-feature-on-or-off"></a>Włączanie lub wyłączanie tej funkcji

Aby można było korzystać z funkcji opisanych w tym artykule, *w systemie muszą być włączone ustawienia użytkownika,* ikony i tytuły kroku nowej funkcji aplikacji magazynowej. Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.25, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Ustawienia użytkownika, ikony i tytuły kroków dla nowej aplikacji magazynowej* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="standard-step-ids-classes-and-icons"></a>Standardowe identyfikatory kroków, klasy i ikony

Każdy krok w przepływie zadań jest identyfikowany za pomocą identyfikatora kroku, a każdy identyfikator kroku ma odpowiednią klasę kroku. Ikona kroku i tytuł są określone w każdej klasie kroku.

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a>Identyfikatory kroków i klasy kroków

W poniższej tabeli wymieniono wszystkie dostępne identyfikatory kroków oraz odpowiadającą im klasę kroku. Jako identyfikator kroku jest używana nazwa formantu podstawowego pola wejściowego.

Przykład pokazujący, jak są używane identyfikatory i klasy kroków, można znaleźć w implementacji metody `WHSMobileAppStepInfoBuilder.stepId()` w sekcji [Przykład: Przydzielanie ikon i tytułów kroków dla przepływu niestandardowego](#example) w dalszej części tego artykułu.

| Identyfikator kroku | Klasa kroku |
|-|-|
| BatchDisposition | WHSMobileAppStepBatchDisposition |
| Przewoźnik | WHSMobileAppStepCarrier |
| CatchWeight | WHSMobileAppStepCatchWeight |
| CatchWeightQtyOutboundWeight | WHSMobileAppStepCatchWeight |
| CatchWeightTag | WHSMobileAppStepCatchWeightTag |
| CatchWeightTagWeight | WHSMobileAppStepCatchWeightTagWeight |
| ChangeWarehouseSuccess | WHSMobileAppStepChangeWarehouseSuccess |
| CheckDigit | WHSMobileAppStepCheckDigit |
| ClusterId | WHSMobileAppStepClusterId |
| ClusterPickQtyVerification | WHSMobileAppStepQtyVerification |
| ClusterPosition | WHSMobileAppStepClusterPosition |
| ConfigId | WHSMobileAppStepConfigId |
| Potwierdzenie | WHSMobileAppStepConfirmation |
| ConsolidateFromLicensePlateId | WHSMobileAppStepConsolidateFromLicensePlateId |
| ConsolidateLPConfirmation | WHSMobileAppStepConsolidateLPConfirmation |
| ConsolidateToLicensePlateId | WHSMobileAppStepConsolidateToLicensePlateId |
| ContainerType | WHSMobileAppStepContainerType |
| CountingReasonCode | WHSMobileAppStepCountingReasonCode |
| CycleCountingAddLPOrFinish | WHSMobileAppStepCycleCountingAddLPOrFinish |
| CycleCountQty1 | WHSMobileAppStepCycleCountQty |
| CycleCountQty2 | WHSMobileAppStepCycleCountQty |
| CycleCountQty3 | WHSMobileAppStepCycleCountQty |
| CycleCountQty4 | WHSMobileAppStepCycleCountQty |
| Disposition | WHSMobileAppStepDisposition |
| DriverCheckInConfirmation | WHSMobileAppStepDriverCheckInConfirmation |
| DriverCheckInId | WHSMobileAppStepDriverCheckInId |
| DriverCheckOutConfirmation | WHSMobileAppStepDriverCheckOutConfirmation |
| DriverCheckOutId | WHSMobileAppStepDriverCheckOutId |
| ExpDate | WHSMobileAppStepExpDate |
| FromBatchDisposition | WHSMobileAppStepFromBatchDisposition |
| FromInventoryStatus | WHSMobileAppStepInventoryStatusFrom |
| FullQty | WHSMobileAppStepFullQty |
| InboundPut | WHSMobileAppStepInboundPut |
| InventBatchId | WHSMobileAppStepBatch |
| InventColorId | WHSMobileAppStepInventColorId |
| InventLocation | WHSMobileAppStepInventLocation |
| InventLocationId | WHSMobileAppStepWarehouse |
| InventSerialId | WHSMobileAppStepInventSerialId |
| InventSizeId | WHSMobileAppStepInventSizeId |
| InventStatusId | WHSMobileAppStepInventStatus |
| InventStyleId | WHSMobileAppStepInventStyleId |
| InventVersionId | WHSMobileAppStepInventVersionId |
| ItemId | WHSMobileAppStepItem |
| ITMContainerID | ITMMobileAppStepContainerId |
| ITMShipmentID | ITMMobileAppStepShipmentId |
| KanbanCardId | WHSMobileAppStepKanbanCard |
| KanbanCardToEmpty | WHSMobileAppStepKanbanCardToEmpty |
| KanbanOrCardId | WHSMobileAppStepKanbanCard |
| LicensePlateId | WHSMobileAppStepLicensePlate |
| LoadId | WHSMobileAppStepLoadId |
| LocationLicensePlatePosition | WHSMobileAppStepLocationLicensePlatePosition |
| LocOrLP | WHSMobileAppStepLocOrLP |
| LocOrLP_From | WHSMobileAppStepLocOrLPFrom |
| LocOrLP_To | WHSMobileAppStepLocOrLPTo |
| LocOrLPCheck | WHSMobileAppStepLocOrLPCheck |
| LocVerification | WHSMobileAppStepLocVerification |
| LPAdjustIn | WHSMobileAppStepLPAdjustIn |
| LPBreakChildLP | WHSMobileAppStepLPBreakChildLP |
| LPBreakParentLP | WHSMobileAppStepLPBreakParentLP |
| LPBuildChildLP | WHSMobileAppStepLPBuildChildLP |
| LPBuildParentLP | WHSMobileAppStepLPBuildParentLP |
| LPVerification | WHSMobileAppStepLPVerification |
| MergeContainerId | WHSMobileAppStepMergeContainerId |
| MixedLPLineNum | WHSMobileAppStepMixedLPLineNum |
| MobileDeviceQueueMessageCollectionIdentifierId | WHSMobileAppStepSelectOrder |
| MovementConfirmCancel | WHSMobileAppStepMovementConfirmCancel |
| NewCaptureWeight | WHSMobileAppStepCatchWeight |
| NewQty | WHSMobileAppStepNewQty |
| OutboundCatchWeightTag | WHSMobileAppStepCatchWeightTag |
| OutboundPut | WHSMobileAppStepOutboundPut |
| OutboundWeight | WHSMobileAppStepCatchWeight |
| OverridePutNewLocation | WHSMobileAppStepOverridePutNewLocation |
| PieceByPieceConfirmation | WHSMobileAppStepQtyVerification |
| POLineNum | WHSMobileAppStepPOLineNum |
| PONum | WHSMobileAppStepPONum |
| PositionFull | WHSMobileAppStepPositionFull |
| PositionFullQty | WHSMobileAppStepPositionFullQty |
| Zawartość | WHSMobileAppStepPotency |
| PrinterName | WHSMobileAppStepPrinterName |
| ProdId | WHSMobileAppStepProdId |
| ProdLastPalletConfirmation | WHSMobileAppStepProdLastPalletConfirmation |
| ProductConfirmation | WHSMobileAppStepProductConfirmation |
| ProductionScrapConfirmation | WHSMobileAppStepProductionScrapConfirmation |
| Odłożenie | WHSMobileAppStepPut |
| PutawayClusterId | WHSMobileAppStepPutawayClusterId |
| Ilość | WHSMobileAppStepQty |
| QtyAdjust | WHSMobileAppStepQtyAdjust |
| QtyShort | WHSMobileAppStepQtyShort |
| QtyToConsume | WHSMobileAppStepQtyToConsume |
| QtyToPick | WHSMobileAppStepQtyToPick |
| QtyToPut | WHSMobileAppStepQtyToPut |
| QtyToScrap | WHSMobileAppStepQtyToScrap |
| QtyVerification | WHSMobileAppStepQtyVerification |
| QtyWithScanningLimit | WHSMobileAppStepQtyAdjust |
| ReasonString | WHSMobileAppStepReasonString |
| RecvLocationId | WHSMobileAppStepRecvLocationId |
| RemoveContainerId | WHSMobileAppStepRemoveContainerId |
| ReprintLabelConfirmation | WHSMobileAppStepReprintLabelConfirmation |
| RMANum | WHSMobileAppStepRMANum |
| ShortPickReason | WHSMobileAppStepShortPickReason |
| SortConOrLP | WHSMobileAppStepSortConOrLP |
| SortLicensePlateId | WHSMobileAppStepSortLicensePlateId |
| SortPositionId | WHSMobileAppStepSortPositionId |
| SortVerification | WHSMobileAppStepSortVerification |
| StartLocationId | WHSMobileAppStepStartLocationId |
| StartProdOrderConfirmation | WHSMobileAppStepStartProdOrderConfirmation |
| TargetLicensePlateId | WHSMobileAppStepTargetLicensePlateId |
| TOLineNum | WHSMobileAppStepTOLineNum |
| ToLocation | WHSMobileAppStepToLocation |
| TONum | WHSMobileAppStepTONum |
| ToWarehouse | WHSMobileAppStepWarehouseTo |
| TransportLoadId | WHSMobileAppStepTransportLoadId |
| WaveLabelId | WHSMobileAppStepWaveLabelId |
| WaveLblQty | WHSMobileAppStepWaveLblQty |
| Masa | WHSMobileAppStepWeight |
| WeightToConsume | WHSMobileAppStepWeightToConsume |
| WHSAdjustmentType | WHSMobileAppStepWHSAdjustmentType |
| WHSReceivingException | WHSMobileAppStepWHSReceivingException |
| WHSWorkException | WHSMobileAppStepWHSWorkException |
| WHSWorkLicensePlateId | WHSMobileAppStepWorkLicensePlateId |
| WMSLocationId | WHSMobileAppStepLocation |
| WorkId | WHSMobileAppStepWorkId |
| WorkIdToCancel | WHSMobileAppStepWorkIdToCancel |
| WorkLPIdPutawayCluster | WHSMobileAppStepWorkLPIdPutawayCluster |
| WorkPoolId | WHSMobileAppStepWorkPoolId |
| ZoneId | WHSMobileAppStepZoneId |

### <a name="available-step-icons"></a><a name="step-icons"></a>Dostępne ikony kroków

System zawiera kolekcję standardowych ikon kroków, których można także używać w niestandardowych krokach. Nie można obecnie przekazywać niestandardowych ikon kroku. W związku z tym należy zawsze wybrać jedną ze standardowych ikon kroków.

W poniższej tabeli pokazano każdą aktualnie dostępną ikonę kroku oraz jej nazwę.

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="Informacje o ikonie kroku"><br>Informacje o</td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Dodaj numer identyfikacyjny lub ikonę kroku pozycji"><br>AddLpOrItem</td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Ikona kroku dyspozycji partii"><br>BatchDisposition</td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Ikona kroku przewoźnika"><br>Przewoźnik</td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Ikona kroku znacznika ilości efektywnej"><br>CatchWeightTag</td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Ikona kroku znacznika ilości efektywnej"><br>CatchWeightTagWeight</td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Ikona kroku cyfry kontrolnej"><br>CheckDigit</td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Ikona kroku ID zameldowania lub wymeldowania"><br>CheckInOutId</td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Ikona kroku podrzędnego — numer identyfikacyjny"><br>ChildLP</td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Ikona kroku identyfikatora grupy"><br>ClusterId</td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Ikona pozycji kroku grupy"><br>ClusterPosition</td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Ikona identyfikatora konfiguracji kroku"><br>ConfigId</td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Ikona skonfigurowanego pola korku"><br>ConfiguredField</td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Ikona kroku Con lub LP"><br>ConOrLP</td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="Konsolidacja z ikony kroku dla identyfikatora identyfikacyjnego"><br>ConsolidateFromLicensePlateID</td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="Konsolidacja do ikony kroku dla identyfikatora identyfikacyjnego"><br>ConsolidateToLicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Ikona kroku typu kontenera"><br>ContainerType</td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Ikona kroku inwentaryzacji"><br>Inwentaryzacja</td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Ikona kroku kodu przyczyny inwentaryzacji"><br>CountingReasonCode</td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Ikona kroku kodu kraju pochodzenia"><br>CountryOfOrigin</td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Ikona kroku dyspozycji"><br>Disposition</td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Ikona Krok gotowe"><br>Zakończono</td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Ikona kroku potwierdzenia odprawy kierowcy"><br>DriverCheckInConfirmation</td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Ikona kroku identyfikacji kierowcy"><br>DriverCheckInId</td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Ikona kroku zakończenia identyfikacji kierowcy"><br>DriverCheckOutId</td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Ikona kroku daty ważności"><br>ExpDate</td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Ikona skonfigurowanego pola"><br>Pole</td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Ikona kroku dyspozycji partii od"><br>FromBatchDisposition</td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Ikona Krok stanu magazynu z"><br>FromInventoryStatus</td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Ikona kroku identyfikatora atrybutu"><br>IdAttribute</td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Ikona kroku identyfikatora partii zapasów"><br>InventBatchID</td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Ikona kroku identyfikatora koloru"><br>InventColorID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Ikona kroku identyfikatora lokalizacji"><br>InventLocation</td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Ikona kroku identyfikatora serializowania"><br>InventSerialID</td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Ikona kroku identyfikatora rozmiaru"><br>InventSizeID</td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Ikona kroku identyfikatora stanu zapasów"><br>InventStatusID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Ikona kroku identyfikatora stylu"><br>InventStyleID</td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Ikona kroku identyfikatora wersji zapasów"><br>InventVersionID</td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Ikona identyfikatora elementu kroku"><br>ItemID</td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="Ikona kroku identyfikatora kontenera ITM"><br>ITMContainerID</td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="Ikona kroku identyfikatora wysyłki ITM"><br>ITMShipmentID</td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Ikona kroku identyfikatora karty Kanban"><br>KanbanCardID</td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Ikona kroku identyfikatora karty lub Kanban"><br>KanbanOrCardID</td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Ikona kroku — numer identyfikacyjny"><br>LicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Ikona identyfikatora ładowania kroku"><br>LoadId</td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Ikona stopnia położenia numeru identyfikacyjnego"><br>LocationLicensePlatePosition</td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Ikona kroku lokalizacji lub numeru identyfikacyjnego"><br>LocOrLP</td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Ikona kroku lokalizacji lub sprawdzania numeru identyfikacyjnego"><br>LocOrLPCheck</td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Ikona kroku od lokalizacji lub numeru identyfikacyjnego"><br>LocOrLPFrom</td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Ikona kroku lokalizacji lub numeru identyfikacyjnego do"><br>LocOrLPTo</td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Ikona kroku zakończonego długiego procesu"><br>LongProcessCompleted</td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Ikona kroku nadrzędnego LP podziału LP"><br>LPBreakParentLP</td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Ikona kroku identyfikatora kontenera scalania"><br>MergeContainerId</td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Ikona kroku numeru mieszanego numeru identyfikacyjnych"><br>MixedLPLineNum</td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Ikona kroku wagi wychodzącej"><br>OutboundWeight</td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Ikona kroku właściciela"><br>Właściciel</td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Ikona kroku nadrzędnego — numer identyfikacyjny"><br>ParentLP</td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Potwierdź ikonę kroku"><br>PleaseConfirm</td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Ikona kroku numeru linii zamówienia"><br>POLineNum</td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Ikona kroku numeru zamówienia"><br>PONum</td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Ikona pełnego kroku pozycji"><br>PositionFull</td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Ikona kroku zawartości"><br>Zawartość</td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Ikona kroku nazwy drukarki"><br>PrinterName</td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Ikona identyfikatora produkcji kroku"><br>ProdId</td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Ikona kroku potwierdzenia produktu"><br>ProductConfirmation</td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Informacje o dodaniu kroku"><br>Odłożenie</td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Ikona kroku identyfikatora grupy odłożenia"><br>PutawayClusterId</td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Ikona Kroku ilości"><br>Ilość</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Korygowanie ilości w ikonie kroku"><br>QtyAdjustIn</td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Ikona krótkiego kroku ilości"><br>QtyShort</td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Ikona Ilości do zużywania w kroku"><br>QtyToConsume</td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Ikona Ilości do dołożenia w kroku"><br>QtyToPut</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Ikona Ilości do odrzucenia w kroku"><br>QtyToScrap</td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Ikona kroku potwierdzenia ilości"><br>QuantityConfirmation</td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Ikona kroku zadania zakończenia zgłoszenia jako gotowego"><br>RAFEndJob</td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Ikona kroku identyfikatora lokalizacji odbierania"><br>RecvLocationID</td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Ikona kroku identyfikatora kontenera usuwania"><br>RemoveContainerID</td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="Ikona stopnia numeru RMA"><br>RMANum</td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Wybierz ikonę kolejność kroków"><br>SelectOrder</td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Ikona krótkiego kroku uzasadnienia wyboru"><br>ShortPickReason</td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Ikona kroku identyfikatora stanowiska sortowania"><br>SortPositionId</td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Ikona kroku — docelowy numer identyfikacyjny"><br>TargetLicensePlateId</td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Ikona Krok numeru wiersza do"><br>ToLineNum</td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Ikona kroku identyfikatora lokalizacji do"><br>ToLocation</td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Ikona kroku numeru do"><br>ToNum</td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Ikona kroku magazynu do"><br>ToWarehouse</td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Ikona stopnia identyfikacji ładunku transportowego"><br>TransportLoadId</td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Ikona kroku ID partii dostawcy"><br>VendBatchId</td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Ikona kroku identyfikatora etykiety grupy czynności"><br>WaveLabelId</td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Ikona kroku etykiety jakości grupy czynności"><br>WaveLblQty</td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Ikona kroku wagi"><br>Masa</td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Ikona wagi do zużywania w kroku"><br>WeightToConsume</td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WMS adjustment type step icon" title="Ikona kroku dostosowania magazynu"><br>WHSAdjustmentType</td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WMS receiving exception step icon" title="Ikona kroku wyjątku odbioru WMS"><br>WHSReceivingException</td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="Ikona kroku ID lokalizacji WMS"><br>WMSLocationID</td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Ikona stopnia Work ID"><br>WorkId</td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Identyfikator pracy do anulowania ikony kroku"><br>WorkIdToCancel</td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Ikona kroku — numer identyfikacyjny pracy"><br>WorkLicensePlateId</td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Ikona kroku — numer identyfikacyjny grupy odłożenia"><br>WorkLPIDPutawayCluster</td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Ikona puli identyfikatora pracy"><br>WorkPoolID</td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Ikona stopnia identyfikatora strefy"><br>ZoneID</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a>Przykład: Przypisywanie ikon i tytułów kroków dla przepływu niestandardowego

Ten przykład wyjaśnia, jak ustawić ikony i tytuły kroków dla niestandardowego przepływu zadań. Scenariusz jest zbudowany na przykładzie niestandardowego przepływu zadań, który jest przedstawiony i zbadany bardziej szczegółowo w poniższym wpisie na blogu: [Dostosowywanie w aplikacji mobilnej Warehousing](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app). Przepływ zadań działa w następujący sposób:

1. Aplikacja wyświetla stronę, na której pracownik proszony jest o podanie identyfikatora pojemnika (np. poprzez zeskanowanie kodu kreskowego).
1. Jeśli identyfikator pojemnika jest prawidłowy, aplikacja otwiera nową stronę, na której pracownik proszony jest o podanie wagi. (Jeśli identyfikator kontenera nie jest poprawny, pracownik wraca na pierwszą stronę).
1. Gdy pracownik wprowadzi prawidłową wagę, system zapisuje wagę i odsyła pracownika na pierwszą stronę.

Poniższa ilustracja przedstawia ten przepływ zadań.

![Diagram przepływu zadania.](media/step-icons-example-task-flow.png "Diagram przepływu zadania")

### <a name="create-a-step-class-for-the-container-input-page"></a>Utwórz klasę kroku dla strony wejściowej kontenera

Strona wprowadzania danych o pojemniku umożliwia pracownikowi zeskanowanie lub wprowadzenie identyfikatora pojemnika.

![Strona danych wejściowych kontenera.](media/step-icons-example-container-input.png "Strona danych wejściowych kontenera")

Na stronie wprowadzania danych w kontenerze, nazwa kontrolki dla pola wejściowego to `ContainerId`. Ta nazwa formantu nie znajduje się na [liście identyfikatorów kroków](#step-ids-classes), więc nie będzie można odnaleźć istniejącego kroku opartego na tej nazwie. Dlatego musisz utworzyć klasę kroku, która będzie reprezentować krok. Oto przykład.

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

Identyfikator ikony kroku jest przechowywany w klasie członka `defaultStepIcon`, a tytuł kroku jest przechowywany w klasie członka `defaultStepTitle`.

Aby przypisać ikonę kroku, ustaw jeden z identyfikatorów `defaultStepIcon` na ikonę wymienioną w sekcji [Dostępne ikony kroków](#step-icons) wcześniej w tym artykule.

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a>Użyj standardowej lub niestandardowej ikony kroku i tytułu dla wprowadzanej wagi

Strona wprowadzania wagi pozwala pracownikowi na wprowadzenie wagi.

![Strona wprowadzania wagi.](media/step-icons-example-weight-input.png "Strona wprowadzania wagi")

Na stronie wprowadzania wagi nazwa formantu pola wejściowego `Weight` znajduje się na [liście identyfikatorów kroków](#step-ids-classes). Jeśli więc ikona kroku i tytuł zdefiniowane w klasie `WHSMobileAppStepWeight` są dla Ciebie akceptowane, nie musisz nic zmieniać w tym kroku.

Jeśli jednak w tym kroku preferujesz użycie innej ikony lub tytułu, możesz zastąpić metodę `stepId()` lub metodę `stepInfo()` w klasie konstruktora. Każdy przepływ zadania ma własny konstruktor informacji krokowych.

#### <a name="override-the-stepid-method"></a>Zastąp metodę stepId()

W tym przykładzie pokazano jeden sposób modyfikowania klasy konstruktora przez zastąpienie metody `stepId()`.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

Następnie należy utworzyć klasę kroku `NewWeight` dla tego kroku. Kod powinien przypominać kod dla przykładu `ContainerId` pokazanego wcześniej w tym artykule.

#### <a name="override-the-stepinfo-method"></a>Zastąp metodę stepInfo()

W tym przykładzie pokazano jeden sposób modyfikowania klasy konstruktora przez zastąpienie metody `stepInfo()`.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

Następnie można konstruować obiekt `WHSMobileAppStepInfo` i ustawiać bezpośrednio ikonę i/lub tytuł.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Instalowanie i łączenie aplikacji mobilnej Zarządzanie magazynem](install-configure-warehouse-management-app.md)
- [Ustawienia użytkownika urządzenia przenośnego](mobile-device-user-settings.md)
