---
title: Dodatek Widoczność magazynu — omówienie
description: W tym temacie wyjaśniono, czym jest dodatek Widoczność magazynu i jakie są jego funkcje.
author: yufeihuang
ms.date: 10/26/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8871d10dac9103f17780989bc547b6c20ba79b76
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985553"
---
# <a name="inventory-visibility-add-in-overview"></a>Dodatek Widoczność magazynu — omówienie

[!include [banner](../includes/banner.md)]

Dodatek Widoczność magazynu (zwany także *Widoczność magazynu*) jest niezależną i wysoko skalowalną mikrodostępną usługą, która umożliwia śledzenie dostępnych zapasów w czasie rzeczywistym. Udostępnia zatem globalny widok zapasów.

Zewnętrzne systemy mają dostęp do usługi za pośrednictwem interfejsów API RESTful. W ten sposób mogą albo wykonać zapytanie o dostępne zapasy w danych zestawach wymiarów, albo wprowadzić zmiany w zapasach w różnych niestandardowych źródłach danych.

Jako mikrousługa oparta na Microsoft Dataverse, dodatek Widoczność magazynu jest rozszerzalny. Aplikacje można tworzyć przy użyciu Power Apps. Ponadto, stosując Power BI można dostarczyć funkcje spełniające indywidualne wymagania.

Dodatek Widoczność magazynu można zintegrować z wieloma systemami innych firm, ustawiając opcje konfiguracji standardowych wymiarów magazynowych oraz ustawiając typy transakcji. Dodatek Widoczność magazynu obsługuje również niestandardowe możliwości rozszerzania za pomocą konfigurowalnych obliczonych ilości.

## <a name="inventory-visibility-integration-with-dynamics-365-supply-chain-management"></a>Integracja dodatku Widoczność magazynu z Dynamics 365 Supply Chain Management

Zintegrowane rozwiązanie ściąga dane magazynowe z Dynamics 365 Supply Chain Management i w sposób ciągły śledzi zmiany zapasów. Aby uzyskać więcej informacji, zobacz temat [Instalowanie i konfigurowanie dodatku Widoczność magazynu](inventory-visibility-setup.md) oraz [Konfigurowanie dodatku Widoczność magazynu](inventory-visibility-configuration.md).

## <a name="get-a-global-view-of-inventory"></a>Uzyskiwanie widoku globalnego zapasów

Zintegrowane rozwiązanie umożliwia definiowanie własnych źródeł danych i centralizowanie danych magazynowych. Więcej informacji zawiera temat [Konfigurowanie dodatku Widoczność magazynu](inventory-visibility-configuration.md).

Dostępne są dwa sposoby wyświetlania zapasów:

- Przesłanie zapytania za pomocą interfejsu API o wysokiej wydajności. Ten interfejs API może zwracać dane magazynowe w czasie rzeczywistym bezpośrednio z pamięci podręcznej. Umowy i przykłady można znaleźć w [interfejsach publicznych API dodatku Widoczność magazynu](inventory-visibility-api.md).
- Wyświetlanie nieprzetworzonej listy dostępnych zapasów. Ta lista jest okresowo synchronizowana z pamięcią podręczną i jest widoczna w Dataverse. Więcej informacji zawiera temat [Aplikacja Widoczność magazynu](inventory-visibility-power-platform.md).

## <a name="soft-reservations"></a>Rezerwacje wstępne

Rezerwacja wstępna ma zastosowanie, gdy firma musi zarezerwować określoną ilość produktów, aby na przykład uniknąć niedoborów podczas realizacji zamówień sprzedaży. Gdy zamówienie sprzedaży zostanie utworzone i potwierdzone w Supply Chain Management lub innym systemie zarządzania zamówieniami, żądanie rezerwacji ilości jest wysyłane do dodatku Widoczność magazynu. Widoczność magazynu umożliwia rezerwowanie produktów, które mają szczegóły wymiarów oraz określone typy transakcji magazynowych. (Więcej informacji zawiera temat [Aplikacja Widoczność magazynu](inventory-visibility-power-platform.md)). Gdy ilość zostanie zarezerwowana, zwracany jest identyfikator rezerwacji. Tego identyfikatora rezerwacji można użyć w celu połączenia z oryginalnym zamówieniem w Supply Chain Management lub innym systemie zarządzania zamówieniami.

Ta funkcja jest tak zaprojektowana, że rezerwacja w dodatku Widoczność magazynu nie zmienia całkowitej ilości. Oznacza tylko zarezerwowaną ilość. (Dlatego taka rezerwacja jest nazywana *rezerwacją wstępną*). Ilość zarezerwowana wstępnie może zostać zrekompensowana, gdy produkty są zużywane w Supply Chain Management lub w systemie innej firmy, poprzez ponowne wywołanie interfejsu API w celu odjęcia ilości i zaktualizowania ilości całkowitej w dodatku Widoczność magazynu. Więcej informacji zawiera temat [Rezerwacje dodatku Widoczność magazynu](inventory-visibility-reservations.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
