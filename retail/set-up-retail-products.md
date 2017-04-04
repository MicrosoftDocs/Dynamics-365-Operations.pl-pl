---
title: "Konfigurowanie produktów sieci sprzedaży"
description: "W tym artykule opisano konfigurowanie produktów sieci sprzedaży w Microsoft Dynamics 365 dla operacji - sieci sprzedaży."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 116c49174989ff14982027cc235640c2ad7322f2
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-retail-products"></a>Konfigurowanie produktów sieci sprzedaży

W tym artykule opisano konfigurowanie produktów sieci sprzedaży w Microsoft Dynamics 365 dla operacji - sieci sprzedaży.

Zanim mogą oferować produkty w celu odsprzedaży w kanałach sieci sprzedaży, należy utworzyć i skonfigurować produkty w usłudze Dynamics 365 dla operacji systemu AX - sieci sprzedaży. Handel detaliczny używa funkcji produktu w usłudze Dynamics 365 dla operacji do tworzenia produktów całej organizacji w produktu głównego. Można utworzyć produkty, zdefiniować ich właściwości i atrybuty oraz przypisać produkty do hierarchii kategorii sieci sprzedaży. Aby udostępnić produkty w kanałach sprzedaży detalicznej i dodać je do aktywnego asortymentu, trzeba je zwolnić dla firm, w których są dostępne. Aby skonfigurować produkty sprzedawane w kanałach sprzedaży detalicznej, należy wykonać następujące zadania.

1.  Skonfiguruj hierarchię produktów w sieci sprzedaży. Za pomocą funkcji hierarchii kategorii w Dynamics 365 dla operacji, można zdefiniować hierarchii kategorii sieci sprzedaży do grupowania i kategoryzacji produktów dostarczanych do kanałów sprzedaży detalicznej. Atrybuty definiowane przez użytkownika i system można określać na poziomie kategorii. Następnie wszystkie produkty, które są przypisane do kategorii, dziedziczą te atrybuty. Można zdefiniować wiele hierarchii kategorii, a każdy produkt może być przypisany do wielu hierarchii. Jednak w jednej hierarchii każdy produkt może być przypisany tylko do jednej kategorii.
2.  Dodaj produkty i warianty produktów do produktu głównego. Produkty, które są dodawane do produktu głównego reprezentują globalną listę produktów. Można dodawać produkty pojedynczo ręcznie lub zaimportować dane produktów od dostawców.
3.  Wydanie produktów firmom. Tylko zatwierdzone produkty, które zostały zwolnione dla firmy mogą być dostępne dla kanałów sprzedaży detalicznej. Jeśli definiujesz produkt po raz pierwszy, definiowanie odbywa się na poziomie organizacji. Następnie można wybrać jedną lub więcej firm, do których produkty zostaną zwolnione. Produkt staje się dostępny dla wielu kanałów sprzedaży detalicznej w całej organizacji. Można użyć tej funkcji do tworzenia produktu jeden raz, dodawania i aktualizowania atrybutów i właściwości w jednym miejscu, a następnie dystrybuowania produktu wewnątrz organizacji do kanałów sprzedaży.
4.  Dodawanie produktów do asortymentu. Asortyment reprezentuje kolekcję produktów, które oferujesz w kanałach sprzedaży detalicznej. Można zdefiniować jeden lub kilka asortymentów, a każdy produkt można włączyć do jednego lub większej liczby asortymentów. Aby przypisać produkty do kanałów sprzedaży, należy przypisać asortymenty do kanałów sprzedaży. Podczas tworzenia asortymentu można dodać produkty, które jeszcze nie zostały zwolnione do firmy. Trzeba jednak zwolnić produkty do firmy przed udostępnieniem ich w kanałach sprzedaży detalicznej.
5.  Dodaj produkty do hierarchii nawigacji. Zanim produkty mogą być przeglądane przez Internet lub punkcie sprzedaży (POS), muszą być sklasyfikowani w hierarchii nawigacji sprzedaży.
6.  Dodaj produkty do katalogów. Ten krok jest opcjonalny dla OP, sklepów internetowych wymagają, aby produkty objęte co najmniej jeden katalog.



