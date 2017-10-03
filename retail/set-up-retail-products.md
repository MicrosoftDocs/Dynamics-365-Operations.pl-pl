---
title: "Konfigurowanie produktów sieci sprzedaży"
description: "W tym artykule opisano, jak konfigurować produkty sieci sprzedaży w programie Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 2be44e0000e9730aa93076f21a4204f5d56f6aac
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017

---

# <a name="set-up-retail-products"></a>Konfigurowanie produktów detalicznych

[!include[banner](includes/banner.md)]


W tym artykule opisano, jak konfigurować produkty sieci sprzedaży w programie Microsoft Dynamics 365 for Retail.

Aby móc odsprzedawać produkty w kanałach sprzedaży detalicznej, musisz utworzyć i skonfigurować te produkty w rozwiązaniu Dynamics 365 for Retail. Handel detaliczny używa funkcji produktów w programie Dynamics 365 for Retail do tworzenia produktów na poziomie organizacji w produkcie głównym. Można utworzyć produkty, zdefiniować ich właściwości i atrybuty oraz przypisać produkty do hierarchii kategorii sieci sprzedaży. Aby udostępnić produkty w kanałach sprzedaży detalicznej i dodać je do aktywnego asortymentu, trzeba je zwolnić dla firm, w których są dostępne. Aby skonfigurować produkty sprzedawane w kanałach sprzedaży detalicznej, należy wykonać następujące zadania.

1.  Skonfiguruj hierarchię produktów w sieci sprzedaży. Za pomocą funkcji hierarchii kategorii w programie Dynamics 365 for Retail można zdefiniować hierarchie kategorii sieci sprzedaży do grupowania i klasyfikować produktów dystrybuowanych do kanałów sprzedaży detalicznej. Atrybuty definiowane przez użytkownika i system można określać na poziomie kategorii. Następnie wszystkie produkty, które są przypisane do kategorii, dziedziczą te atrybuty. Można zdefiniować wiele hierarchii kategorii, a każdy produkt może być przypisany do wielu hierarchii. Jednak w jednej hierarchii każdy produkt może być przypisany tylko do jednej kategorii.
2.  Dodaj produkty i warianty produktów do produktu głównego. Produkty, które są dodawane do produktu głównego reprezentują globalną listę produktów. Można dodawać produkty pojedynczo ręcznie lub zaimportować dane produktów od dostawców.
3.  Wydanie produktów firmom. Tylko zatwierdzone produkty, które zostały zwolnione dla firmy mogą być dostępne dla kanałów sprzedaży detalicznej. Jeśli definiujesz produkt po raz pierwszy, definiowanie odbywa się na poziomie organizacji. Następnie można wybrać jedną lub więcej firm, do których produkty zostaną zwolnione. Produkt staje się dostępny dla wielu kanałów sprzedaży detalicznej w całej organizacji. Można użyć tej funkcji do tworzenia produktu jeden raz, dodawania i aktualizowania atrybutów i właściwości w jednym miejscu, a następnie dystrybuowania produktu wewnątrz organizacji do kanałów sprzedaży.
4.  Dodawanie produktów do asortymentu. Asortyment reprezentuje kolekcję produktów, które oferujesz w kanałach sprzedaży detalicznej. Można zdefiniować jeden lub kilka asortymentów, a każdy produkt można włączyć do jednego lub większej liczby asortymentów. Aby przypisać produkty do kanałów sprzedaży, należy przypisać asortymenty do kanałów sprzedaży. Podczas tworzenia asortymentu można dodać produkty, które jeszcze nie zostały zwolnione do firmy. Trzeba jednak zwolnić produkty do firmy przed udostępnieniem ich w kanałach sprzedaży detalicznej.
5.  Dodawanie produktów do hierarchii nawigacji. Aby można było przeglądać produkty online lub w punkcie sprzedaży, muszą zostać sklasyfikowane w hierarchii nawigacji sieci sprzedaży.
6.  Dodawanie produktów do katalogów. Mimo że ten krok jest opcjonalny dla punktu sprzedaży, sklepy internetowe wymagają umieszczenia produktów w co najmniej jednym katalogu.





