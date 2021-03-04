---
title: Zarządzanie transportem — omówienie
description: W tym temacie omówiono funkcjonalność zarządzania transportem dostępną w rozwiązaniu Supply Chain Management.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSParameters,TMSRateRouteWorkbench, WHSLoadPlanningWorkbench, TMSLoadBuildTemplateApply, WHSLoadTemplate, TMSTransportationStatus, TMSLoadSeal, TMSLoadBuildProposal, TMSLoadBuildWorkbench, TMSLoadBuildStrategy, TMSLoadBuildStrategyAttributeValue
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4affc5846ee329a4571d6fb3e0c42873387241ad
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435591"
---
# <a name="transportation-management-overview"></a>Omówienie zarządzania transportem

[!include [banner](../includes/banner.md)]

W tym temacie omówiono funkcjonalność zarządzania transportem dostępną w rozwiązaniu Supply Chain Management.

Moduł Zarządzanie transportem pozwala korzystać z transportu w firmie oraz identyfikować dostawców i rozwiązania wyboru trasy dla zamówień przychodzących i wychodzących. Można na przykład określić najszybszą trasę lub najtańszą stawkę za wysyłkę. W poniższej tabeli opisano główne scenariusze używania zarządzania transportem.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenariusz</th>
<th>Jak może pomóc moduł Zarządzanie transportem</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Korzystanie z zewnętrznych operatorów logistycznych do obsługi transportu.</td>
<td>Modułu zarządzania transportem można używać do obsługi transportu przychodzącego i/lub wychodzącego.</td>
</tr>
<tr class="even">
<td>Własna flota firmy jest dostępna do obsługi dostaw/odbiorów, a opłaty za dostawę są przenoszone na odbiorców.</td>
<td>W procesach transportu wychodzącego moduł Zarządzanie transportu może służyć do obliczania opłat transportowych i przenoszenia ich na odbiorców. Nie jest przy tym konieczny proces uzgadniania faktur z przewoźnikiem.</td>
</tr>
<tr class="odd">
<td>Własna flota firmy jest dostępna do obsługi dostaw/odbiorów, ale opłaty za dostawę nie są przenoszone na odbiorców, ponieważ koszt transportu jest zawarty w cenie produktu.</td>
<td>Wiele funkcji zarządzania transportem nie jest potrzebnych. Można jednak za pomocą tego modułu obliczać stawki transportowe i odpowiednio korygować ceny sprzedaży.</td>
</tr>
<tr class="even">
<td>Usługi logistyczne są świadczone przez inną firmę w tej samej organizacji.</td>
<td><ul>
<li>Można używać modułu Zarządzanie transportem, traktując tę firmę jak każdego innego przewoźnika. Nie można zautomatyzować transakcji ekonomicznych między wewnętrznymi firmami. W związku z tym należy obsługiwać te transakcje ręcznie (na przykład przez tworzenie zamówień zakupu).</li>
<li>W firmie świadczącej usługi logistyczne moduł zarządzania transportem może służyć do obliczania stawek transportowych.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-supply-chain-management"></a>Planowanie transportu w Supply Chain Management
W module Zarządzanie transportem planowania transportu może być oparte na zamówieniach lub na wysyłkach tworzonych w oparciu o te zamówienia. Wysyłki zawsze się pojawiają w pewnym momencie, ale nie są wymagane do planowania transportu. Zamówienia przeniesienia są częścią scenariusza transportu wychodzącego i mogą być planowane razem z zamówieniami sprzedaży. 

![Rysunek ładunku](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a>Transport przychodzący
Gdy zamawiasz towary od dostawcy i muszą one zostać dostarczone do Twojego magazynu, można samodzielnie zorganizować transport. Rozwiązanie Supply Chain Management umożliwia zaplanowanie transportu i przyjęcia przychodzącego ładunku. Poniższy rysunek przedstawia przepływ procesu biznesowego dla planowania transportu towarów przychodzących. 

![Przebieg procesu biznesowego przychodzącego transportu ładunku](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a>Transport wychodzący
Można planować i przetwarzać ładunki wychodzące w celu wysłania określonych towarów z magazynu firmy do odbiorcy. Rozwiązanie Supply Chain Management umożliwia zaplanowanie transportu i wysyłki wychodzącego ładunku. Poniższy rysunek przedstawia przepływ procesu biznesowego planowania i przetwarzania obciążenia wychodzącego dla ładunku. 

![Planowanie i przetwarzania ładunków wychodzących](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a>Kompilowanie ładunku
Supply Chain Management zawiera strategię kompilowania ładunku o nazwie Strategia kompilowania ładunku na podstawie objętości. Pozwala ona stosować maksymalne wartości wysokości i wagi określone w szablonie ładunku albo zastępować te ustawienia wprowadzaniem nowych wartości. Aby użyć tej strategii, zaznacz ją w polu **Strategia kompilowania ładunku** na skróconej karcie **Ustawienia** na karcie **Pulpit kompilowania ładunku**. Ponadto można dodawać własne strategie kompilowania ładunku przez utworzenie nowej klasy w drzewie obiektów aplikacji (AOT).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]