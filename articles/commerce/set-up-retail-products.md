---
title: Konfigurowanie produktów detalicznych
description: W tym artykule opisano, jak konfigurować produkty sieci sprzedaży w programie Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailProductAndCategoryWorkspace, EcoResProductDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e8f624f5feb8ee8f641a9b35ae31bdfe38e5e0ce
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023690"
---
# <a name="set-up-retail-products"></a>Konfigurowanie produktów sprzedaży detalicznej

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak konfigurować produkty w programie Dynamics 365 Commerce.

Aby móc oferować produkty w kanałach handlowych do ponownej sprzedaży, musisz utworzyć i skonfigurować te produkty. Commerce tworzy produkty w całej organizacji, znajdujące się w danych głównych produktu. Możesz utworzyć produkty, zdefiniować ich właściwości i atrybuty oraz przypisać produkty do hierarchii kategorii handlowej. Aby udostępnić produkty w kanałach i dodać je do aktywnego asortymentu, musisz zwolnić je do firm, w których są one dostępne. Aby skonfigurować produkty sprzedawane w kanałach, należy wykonać następujące zadania.

1. **Skonfiguruj hierarchię produktów.** Za pomocą funkcji hierarchii kategorii w programie Commerce można zdefiniować hierarchie kategorii sieci sprzedaży do grupowania i klasyfikować produktów dystrybuowanych do kanałów. Atrybuty definiowane przez użytkownika i system można określać na poziomie kategorii. Następnie wszystkie produkty, które są przypisane do kategorii, dziedziczą te atrybuty. Można zdefiniować wiele hierarchii kategorii, a każdy produkt może być przypisany do wielu hierarchii. Jednak w jednej hierarchii każdy produkt może być przypisany tylko do jednej kategorii.
2. **Dodaj produkty i warianty produktów do produktu głównego.** Produkty, które są dodawane do produktu głównego reprezentują globalną listę produktów. Można dodawać produkty pojedynczo ręcznie lub zaimportować dane produktów od dostawców.
3. **Wydanie produktów firmom.** Tylko zatwierdzone produkty, które zostały zwolnione dla firm mogą być dostępne dla kanałów. Jeśli definiujesz produkt po raz pierwszy, definiowanie odbywa się na poziomie organizacji. Następnie można wybrać jedną lub więcej firm, do których produkty zostaną zwolnione. Produkt staje się dostępny dla wielu kanałów w całej organizacji. Można użyć tej funkcji do tworzenia produktu jeden raz, dodawania i aktualizowania atrybutów i właściwości w jednym miejscu, a następnie dystrybuowania produktu wewnątrz organizacji.
4. **Dodawanie produktów do asortymentu.** Asortyment reprezentuje kolekcję produktów, które oferujesz w kanałach. Można zdefiniować jeden lub kilka asortymentów, a każdy produkt można włączyć do jednego lub większej liczby asortymentów. Aby przypisać produkty do kanałów, należy przypisać asortymenty do tych kanałów. Podczas tworzenia asortymentu można dodać produkty, które jeszcze nie zostały zwolnione do firmy. Trzeba jednak zwolnić produkty do firmy przed udostępnieniem ich w kanałach.
5. **Dodawanie produktów do hierarchii nawigacji.** Aby można było przeglądać produkty online lub w punkcie sprzedaży, muszą zostać sklasyfikowane w hierarchii nawigacji Commerce.
6. **Dodawanie produktów do katalogów.** Mimo że ten krok jest opcjonalny dla punktu sprzedaży, sklepy internetowe wymagają umieszczenia produktów w co najmniej jednym katalogu.
