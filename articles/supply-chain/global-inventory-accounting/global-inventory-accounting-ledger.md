---
title: Księga Globalnego księgowania zapasów
description: Ten temat opisuje księgi Globalnego księgowania zapasów, które są zdefiniowane przez połączenie waluty, kalendarza, konwencji i powiązania z osobą prawną.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea3434675aa3b7f2304be93ef9b489747994fa9d
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273208"
---
# <a name="global-inventory-accounting-ledger"></a>Księga Globalnego księgowania zapasów

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Globalne księgowanie zapasów ma własny zestaw ksiąg. Za każdym razem, gdy dla danej osoby prawnej przetwarzana jest transakcja związana z inwentaryzacją, system może ją zaksięgować w dowolnej liczbie ksiąg Globalnej księgi zapasów, w zależności od potrzeb.

Księga główna to rejestr środków debetowych i kredytowych. Środki te są klasyfikowane za pomocą elementów kosztów i kont księgi głównej. Księga Globalnego księgowania zapasów jest zdefiniowana przez połączenie waluty, kalendarza, konwencji i powiązania z osobą prawną.

Aby skonfigurować księgi Globalnego księgowania zapasów, przejdź do **Globalnego księgowania zapasów \> Konfiguracji \> Ksiąg Globalnego księgowania zapasów**. Dla każdej księgi ustaw następujące pola:

- **Nazwa** — Wprowadź nazwę księgi.
- **Opis** – wprowadź opis księgi.
- **Kalendarz obrachunkowy** — umożliwia określenie kalendarza obrachunkowego księgi.
- **Waluta i typ kursu wymiany** — pola na tej skróconej karcie umożliwia wybór waluty rozliczeniowej używanej w księdze oraz typ kursu wymiany. W wybranej walucie może być inna niż waluta używana przez podmiot prawny. W przypadku Globalnego księgowania zapasów użytkownicy mogą definiować dowolną liczbę ksiąg wyceny. Globalne księgowanie zapasów obsługuje księgowanie zapasów w wielu walutach i w wielu cenach. Ustaw wartości w następujących polach:

    - **Waluta** — umożliwia wybranie waluty wyceny, w jakiej są zachowywane wartości związane z zapasami. Te wartości obejmują wartość zapasów, koszt własny sprzedaży, zapas w drodze i wszystkie rodzaje odchylenia.
    - **Typ kursu wymiany** — umożliwia wybór kursu wymiany, który system powinien użyć do konwersji kwoty transakcji w walucie transakcji oraz standardowego kosztu towarów na walutę wyceny.

- **Nazwa konwencji** — umożliwia określenie konwencji. Konwencja jest zbiorem zasad, które ustalają sposób księgowania kosztów w tej księdze.
- **Firma** — w księdze będą księgowane dokumenty zaksięgowane dla wybranej firmy.
- **Priming** — umożliwia określenie, czy transakcje magazynowe utworzone przed utworzeniem księgi powinny być przetwarzane zgodnie z walutą i konwencją w księdze. Należy wybrać jedną z następujących opcji:

    - **Aktywacja** — księga powinna przetwarzać transakcje utworzone przed jej utworzeniem.
    - **Dezaktywacja** — księga powinna przetwarzać tylko transakcje utworzone po jej utworzeniu.

    > [!IMPORTANT]
    > Po wprowadzeniu nowych dokumentów **nie** będzie można wrócić do tego pola i poprawić jego wartości.

- **Stan** — System automatycznie ustawia stan nowo utworzonych ksiąg na *Przygotowywanie*.
