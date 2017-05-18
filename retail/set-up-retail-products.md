---
title: "Konfigurowanie produktów sieci sprzedaży"
description: "W tym artykule opisano, jak konfigurować produkty sieci sprzedaży w programie Microsoft Dynamics 365 for Operations — Handel detaliczny."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: 4f565bd5563cbcf9079f3220dd855f41889f1d5e
ms.contentlocale: pl-pl
ms.lasthandoff: 04/26/2017


---

# <a name="set-up-retail-products"></a>Konfigurowanie produktów sieci sprzedaży

[!include[banner](includes/banner.md)]


W tym artykule opisano, jak konfigurować produkty sieci sprzedaży w programie Microsoft Dynamics 365 for Operations — Handel detaliczny.

Zanim będzie można zaoferować produkty do odsprzedaży w kanałach sprzedaży, trzeba utworzyć i skonfigurować produkty w module Dynamics 365 for Operations AX — Handel detaliczny. Handel detaliczny używa funkcji produktów w programie Dynamics 365 for Operations do tworzenia produktów na poziomie organizacji w produkcie głównym. Można utworzyć produkty, zdefiniować ich właściwości i atrybuty oraz przypisać produkty do hierarchii kategorii sieci sprzedaży. Aby udostępnić produkty w kanałach sprzedaży detalicznej i dodać je do aktywnego asortymentu, trzeba je zwolnić dla firm, w których są dostępne. Aby skonfigurować produkty sprzedawane w kanałach sprzedaży detalicznej, należy wykonać następujące zadania.

1.  Skonfiguruj hierarchię produktów w sieci sprzedaży. Za pomocą funkcji hierarchii kategorii w programie Dynamics 365 for Operations można zdefiniować hierarchie kategorii sieci sprzedaży do grupowania i klasyfikować produktów dystrybuowanych do kanałów sprzedaży detalicznej. Atrybuty definiowane przez użytkownika i system można określać na poziomie kategorii. Następnie wszystkie produkty, które są przypisane do kategorii, dziedziczą te atrybuty. Można zdefiniować wiele hierarchii kategorii, a każdy produkt może być przypisany do wielu hierarchii. Jednak w jednej hierarchii każdy produkt może być przypisany tylko do jednej kategorii.
2.  Dodaj produkty i warianty produktów do produktu głównego. Produkty, które są dodawane do produktu głównego reprezentują globalną listę produktów. Można dodawać produkty pojedynczo ręcznie lub zaimportować dane produktów od dostawców.
3.  Wydanie produktów firmom. Tylko zatwierdzone produkty, które zostały zwolnione dla firmy mogą być dostępne dla kanałów sprzedaży detalicznej. Jeśli definiujesz produkt po raz pierwszy, definiowanie odbywa się na poziomie organizacji. Następnie można wybrać jedną lub więcej firm, do których produkty zostaną zwolnione. Produkt staje się dostępny dla wielu kanałów sprzedaży detalicznej w całej organizacji. Można użyć tej funkcji do tworzenia produktu jeden raz, dodawania i aktualizowania atrybutów i właściwości w jednym miejscu, a następnie dystrybuowania produktu wewnątrz organizacji do kanałów sprzedaży.
4.  Dodawanie produktów do asortymentu. Asortyment reprezentuje kolekcję produktów, które oferujesz w kanałach sprzedaży detalicznej. Można zdefiniować jeden lub kilka asortymentów, a każdy produkt można włączyć do jednego lub większej liczby asortymentów. Aby przypisać produkty do kanałów sprzedaży, należy przypisać asortymenty do kanałów sprzedaży. Podczas tworzenia asortymentu można dodać produkty, które jeszcze nie zostały zwolnione do firmy. Trzeba jednak zwolnić produkty do firmy przed udostępnieniem ich w kanałach sprzedaży detalicznej.
5.  Dodawanie produktów do hierarchii nawigacji. Aby można było przeglądać produkty online lub w punkcie sprzedaży, muszą zostać sklasyfikowane w hierarchii nawigacji sieci sprzedaży.
6.  Dodawanie produktów do katalogów. Mimo że ten krok jest opcjonalny dla punktu sprzedaży, sklepy internetowe wymagają umieszczenia produktów w co najmniej jednym katalogu.





