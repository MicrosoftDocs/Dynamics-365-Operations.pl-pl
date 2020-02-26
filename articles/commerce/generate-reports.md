---
title: Generowanie raportów kanału online
description: W tym temacie opisano sposób generowania raportów dotyczących kanału online w Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fd40aabdf40e0f2bb257b914326df5595a0e6945
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003011"
---
# <a name="generate-online-channel-reports"></a>Generowanie raportów kanału online


[!include [banner](includes/banner.md)]

W tym temacie opisano sposób generowania raportów dotyczących kanału online w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Istnieje możliwość generowania i wyświetlania kilku raportów w module Commerce w celu sprawdzenia, jak działa Twój kanał online.

## <a name="channel-summary-report"></a>Raport podsumowania kanału

Raport **podsumowanie kanału** zawiera podsumowanie następujących transakcji dla wybranego kanału:

- Transakcje sprzedaży
- Transakcje płatności
- Transakcje podatkowe
- Transakcje z rabatem

Aby wygenerować raport **podsumowania kanału**, należy wykonać następujące kroki.

1. Przejdź do **Handel detaliczny i inny \> Zapytania i raporty \> Raporty sprzedaży \> Raport podsumowania kanału**.
1. W polu **Od dnia** wprowadź datę.
1. Wprowadź datę w polu **Do dnia**.
1. W polu **kanał** wybierz kanał online.
1. Kliknij przycisk **OK**.
 
## <a name="channel-sales-by-year-report"></a>Raport sprzedaży w kanale wg lat 

Raport **Sprzedaż w kanale wg lat** umożliwia porównanie sprzedaży w ciągu roku dla określonego sklepu. Należy wybrać rok porównywania sprzedaży, a raport porównuje sprzedaż w wybranym roku z sprzedażą za rok poprzedni.

Aby wygenerować **Raport sprzedaży w kanale wg lat**, należy wykonać następujące kroki.

1. Przejdź do **Handel detaliczny i inny \> Zapytania i raporty \> Raporty sprzedaży \> Roczny raport sprzedaży w kanale**.
1. Wprowadź rok w polu **Od roku kalendarzowego**.
1. Wprowadź rok w polu **Do roku kalendarzowego**.
1. W polu **kanał** wybierz kanał online.
1. Kliknij przycisk **OK**.

## <a name="channel-sales-by-hour-report"></a>Raport sprzedaży w kanale wg godzin

Raport **Sprzedaży w kanale wg godzin** umożliwia wyświetlenie metryk sprzedaży na godzinę dla wybranego kanału lub jednostki operacyjnej.

Aby wygenerować **Raport sprzedaży w kanale wg godzin**, należy wykonać następujące kroki.

1. Przejdź do **Handel detaliczny i inny \> Zapytania i raporty \> Raporty sprzedaży \> Godzinowy raport sprzedaży w kanale**.
1. W polu **Od dnia** wprowadź datę.
1. Wprowadź datę w polu **Do dnia**.
1. W polu **kanał** wybierz kanał online.
1. Kliknij przycisk **OK**.

## <a name="top-customers-report"></a>Raport najlepszych odbiorców

Raport **Najlepsi odbiorcy** zawiera metryki sprzedaży dla *N* najlepszych odbiorców dla wybranego kanału lub jednostki operacyjnej. Wartość *N* jest liczbą z przełożenia od 10 do 100 i jest oparta na miary agregacji wybranej przez użytkownika.

Aby wygenerować raport **Najlepsi odbiorcy**, należy wykonać następujące kroki.

1. Przejdź do **Handel detaliczny i inny \> Zapytania i raporty \> Raporty sprzedaży \> Raport najlepszych klientów**.
1. W polu **Od dnia** wprowadź datę.
1. Wprowadź datę w polu **Do dnia**.
1. W polu **kanał** wybierz kanał online.
1. Kliknij przycisk **OK**.

## <a name="top-discounts-report"></a>Raport największych rabatów

Raport **Najlepsze rabaty** zawiera metryki sprzedaży dla *N* najlepszych rabatów dla wybranego kanału lub jednostki operacyjnej. Wartość *N* jest liczbą z przełożenia od 10 do 100 i jest oparta na miary agregacji wybranej przez użytkownika.

Aby wygenerować raport **Najlepsze rabaty**, należy wykonać następujące kroki.

1. Przejdź do **Handel detaliczny i inny \> Zapytania i raporty \> Raporty sprzedaży \> Raport dot. najlepszych zniżek**.
1. W polu **Od dnia** wprowadź datę.
1. Wprowadź datę w polu **Do dnia**.
1. W polu **kanał** wybierz kanał online.
1. Kliknij przycisk **OK**.

## <a name="top-products-report"></a>Raport najlepszych produktów

Raport **Najlepsze produkty** zawiera metryki sprzedaży dla *N* najlepszych produktów dla wybranego kanału lub jednostki operacyjnej. Wartość *N* jest liczbą z przełożenia od 10 do 100 i jest oparta na miary agregacji wybranej przez użytkownika.

Aby wygenerować raport **Najlepsze produkty**, należy wykonać następujące kroki.

1. Przejdź do **Handel detaliczny i inny \> Zapytania i raporty \> Raporty sprzedaży \> Raport dot. najlepszych produktów**.
1. W polu **Od dnia** wprowadź datę.
1. Wprowadź datę w polu **Do dnia**.
1. W polu **kanał** wybierz kanał online.
1. Kliknij przycisk **OK**.

## <a name="category-sales-report"></a>Raport sprzedaży w kategorii

Raport **sprzedaży w kategorii** przedstawia metryki sprzedaży w wybranym okresie dla każdego węzła hierarchii kategorii dla wybranego kanału lub jednostki operacyjnej.

Aby wygenerować raport **Sprzedaży w kategorii**, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Zapytania i raporty \> Raporty sprzedaży \>Raport sprzedaży w kategorii**.
1. W polu **Od dnia** wprowadź datę.
1. Wprowadź datę w polu **Do dnia**.
1. W polu **kanał** wybierz kanał online.
1. Kliknij przycisk **OK**.

## <a name="organization-sales-report"></a>Raport sprzedaży organizacji

Raport **Sprzedaży organizacji** pokazuje wydajność sklepów w jednostce organizacyjnej. Ten raport zawiera ilość sprzedaży i kwotę według sklepu oraz marżę zysku dla każdego sklepu. Jednostka organizacyjna jest oparta na domyślnej hierarchii raportowania.

Aby wygenerować raport **sprzedaży organizacji**, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Zapytania i raporty \> Raporty sprzedaży \> Raport sprzedaży organizacji**.
1. W polu **Od dnia** wprowadź datę.
1. Wprowadź datę w polu **Do dnia**.
1. Kliknij przycisk **OK**.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Zasoby pomocy dla rozwiązania Dynamics 365 Retail](../retail/index.md)
