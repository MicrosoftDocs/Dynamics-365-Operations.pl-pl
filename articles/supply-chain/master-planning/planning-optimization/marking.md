---
title: Oznaczanie zapasów przy użyciu modułu Optymalizacja planowania
description: Ten artykuł zawiera informacje o dostępnych opcjach oznaczania zapasów w zaakceptowanych zamówieniach podczas korzystania z optymalizacji planowania.
author: t-benebo
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2f1902ba76db59b61b0437eb3cd68ee94018b7c5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844476"
---
# <a name="inventory-marking-with-planning-optimization"></a>Oznaczanie zapasów przy użyciu modułu Optymalizacja planowania

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera informacje o dostępnych opcjach oznaczania zapasów w zaakceptowanych zamówieniach podczas korzystania z optymalizacji planowania.

*Oznaczanie* służy do łączenia podaży i popytu. Opcja ta jest podobna do *oznaczania transakcji*, które określa, jak popyt ma zostać pokryty według planowania głównego. Z punktu widzenia planowania główna różnica polega na tym, że oznaczanie jest trwalsze od oznaczania transakcji.

Oznaczanie zostało wprowadzone, by umożliwić obsługę specjalnych scenariuszy wyceny dla metod FIFO (pierwsze na wejściu, pierwsze na wyjściu) i LIFO (ostatnie na wejściu, pierwsze na wyjściu). Obecnie jest także używane do niektórych scenariuszy niezwiązanych z wyceną. Oznaczanie połączeń między podażą a popytem jest opcjonalne i prawie trwałe. Oznaczenie może zostać usunięte przez użytkownika ręcznie lub poprzez uruchomienie rozkładania wierszy zamówienia sprzedaży z zaznaczoną opcją **Usuń oznaczenie**.

Oznaczanie transakcji jest kontrolowane przez planowanie główne na etapie określania zapotrzebowania i ma na celu połączenie popytu z wymaganą podażą. Oznaczanie transakcji można zaktualizować podczas każdego przebiegu planowania, by zoptymalizować podaż potrzebną do pokrycia popytu. Gdy planowanie główne aktualizuje informacje związane z oznaczaniem transakcji, uwzględnia wszelkie istniejące oznaczenia.

Oznaczanie transakcji rozpoczyna się od uwzględnienia stosownych oznaczeń, rezerwacji dostępnych zapasów i rezerwacji zamówionych zapasów w następującej kolejności:

1. Oznaczenia łączące popyt z podażą
1. Rezerwacje dostępnych zapasów
1. Rezerwacje zamówionych zapasów

Podczas akceptowania zamówienia planowanego w oknie dialogowym **Akceptacja** wyświetla się pole **Aktualizacja oznaczenia**, które służy do konfiguracji opcji oznaczania zamówień tworzonych w trakcie akceptowania. Należy wybrać jedną z następujących opcji:

- **Nie** — zapasy nie są oznaczane.
- **Standardowa** — oznaczanie zapasów jest aktualizowane zgodnie z oznaczaniem transakcji. Zamówienie zapotrzebowania (popytu) jest oznaczane na podstawie zamówienia realizacji (podaży). Jeśli w zamówieniu realizacji pozostanie pewna ilość, zamówienie nie zostanie oznaczone, a dane referencyjne będą puste. Na przykład jeśli zamówienie sprzedaży 100 ea otrzyma oznaczenie transakcji łączące je z zamówieniem zakupu 150 ea, informacje referencyjne zostaną przypisane wyłącznie do zamówienia sprzedaży.
- **Rozszerzona** — zarówno zamówienie zapotrzebowania (popyt), jak i zamówienie realizacji (podaż) są oznaczane niezależnie od tego, czy w zamówieniu realizacji pozostaje jakaś ilość. Na przykład jeśli zamówienie sprzedaży 100 ea otrzyma oznaczenie transakcji łączące je z zamówieniem zakupu 150 ea, informacje referencyjne zostaną przypisane zarówno do zamówienia sprzedaży, jak i do zamówienia zakupu.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]