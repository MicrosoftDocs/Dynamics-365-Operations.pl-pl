---
title: "Zarządzanie transportem — omówienie"
description: "W tym temacie omówiono funkcjonalność zarządzania transportem dostępną w programie Microsoft Dynamics 365 for Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 3136fd95c4c56495a391668d6c854a6ae1e36479
ms.lasthandoff: 03/31/2017


---

# <a name="transportation-management-overview"></a>Zarządzanie transportem — omówienie

W tym temacie omówiono funkcjonalność zarządzania transportem dostępną w programie Microsoft Dynamics 365 for Operations.

Moduł Zarządzanie transportem pozwala zarządzać transportem w firmie oraz identyfikować dostawców i rozwiązania wyboru trasy dla zamówień przychodzących i wychodzących. Można na przykład określić najszybszą trasę lub najtańszą stawkę za wysyłkę. W poniższej tabeli opisano główne scenariusze używania zarządzania transportem w programie Microsoft Dynamics 365 for Operations.

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

## <a name="planning-transportation-in-dynamics-365-for-operations"></a>Planowanie transportu w programie Dynamics 365 for Operations
W module Zarządzanie transportem planowania transportu może być oparte na zamówieniach lub na wysyłkach tworzonych w oparciu o te zamówienia. Wysyłki zawsze się pojawiają w pewnym momencie, ale nie są wymagane do planowania transportu. Zamówienia przeniesienia są częścią scenariusza transportu wychodzącego i mogą być planowane razem z zamówieniami sprzedaży. 

![Załadować rysunku](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a>Transport przychodzący
Gdy zamówienie elementów od dostawcy, a towary powinny zostać dostarczone do magazynu, można zorganizować transport elementów samodzielnie. 365 Dynamics dla operacji służy do planowania transportu i przyjęcia ładunku przychodzącego. Poniższy rysunek przedstawia przepływ procesu biznesowego dla planowania transportu towarów przychodzących. 

![Przebieg procesu biznesowego przychodzącego transportu ładunku](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a>Transport wychodzący
Można planować i przetwarzać ładunki wychodzące w celu wysłania określonych towarów z magazynu firmy do odbiorcy. Program Dynamics 365 for Operations może służyć do planowania transportu i wysyłania ładunków wychodzących. Poniższy rysunek przedstawia przepływ procesu biznesowego planowania i przetwarzania obciążenia wychodzącego dla ładunku. 

![Planowanie i przetwarzania wychodzącego obciążenia](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a>Kompilowanie ładunku
Program Dynamics 365 for Operations zawiera strategię kompilowania ładunku o nazwie Strategia kompilowania ładunku na podstawie objętości. Pozwala ona stosować maksymalne wartości wysokości i wagi określone w szablonie ładunku albo zastępować te ustawienia wprowadzaniem nowych wartości. Aby użyć tej strategii, zaznacz ją w polu **Strategia kompilowania ładunku** na skróconej karcie **Ustawienia** na karcie **Pulpit kompilowania ładunku**. Ponadto można dodawać własne strategie kompilowania ładunku przez utworzenie nowej klasy w drzewie obiektów aplikacji (AOT).


