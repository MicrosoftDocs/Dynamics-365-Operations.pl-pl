---
title: Automatyczne rozliczanie i priorytety
description: W tym artykule opisano, jak transakcje są rozliczane po wybraniu opcji Automatyczne rozliczanie na stronie Parametry modułu rozrachunków z odbiorcami. Wyjaśniono również możliwości używania automatycznego rozliczania w połączeniu z priorytetem płatności.
author: ShivamPandey-msft
ms.date: 01/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: kfend
ms.custom: 14531
ms.assetid: e7837cf6-ec69-44b4-8d47-eba38d5c7b1f
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd5b894c82beb1b5d69ad6bf485161ab9c91a806
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855528"
---
# <a name="automatic-settlement-and-prioritization"></a>Automatyczne rozliczanie i priorytety

[!include [banner](../includes/banner.md)]

W tym artykule opisano, jak transakcje są rozliczane po wybraniu opcji Automatyczne rozliczanie na stronie Parametry modułu rozrachunków z odbiorcami. Wyjaśniono również możliwości używania automatycznego rozliczania w połączeniu z priorytetem płatności.

Dostępne są dwie opcje rozliczania płatności za pomocą faktur i innych transakcji. Można ręcznie wybrać transakcje do rozliczenia lub system może wybrać transakcje automatycznie za pomocą funkcji automatycznego rozliczania. Można także dostosować sposób przetwarzania automatycznych rozliczeń przy użyciu opcji **Określanie priorytetów rozliczenia**. Wszystkie te opcje są częścią parametrów rozliczenia określanych na stronie **Parametry modułu rozrachunków z odbiorcami**. Sposób automatycznego rozliczania transakcji może się różnić w zależności od używanej metody automatycznego rozliczania. Dostępne są następujące metody:

-   Priorytet rozliczania zdefiniowany przez użytkownika
-   Domyślne automatyczne rozliczanie

W poniższych sekcjach opisano sposób rozliczania transakcji w przypadku każdej z metod.

## <a name="example-transactions"></a>Przykładowe transakcje
Przykłady rozliczeń w dalszej części tego artykułu są oparte na następujących transakcjach. Wszystkie transakcje dotyczą odbiorcy 2050.

| Transakcja   | Data        | Kwota | Warunki rabatu gotówkowego | Data rabatu | Komentarze                                                                                                                                                                                      |
|---------------|-------------|--------|---------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Faktura 1     | 15 sierpnia   | 100,00 | 2%14, Netto 30        | 29 sierpnia          |                                                                                                                                                                                               |
| Faktura 2     | 1 września | 250.00 | 2%14, Netto 30        | 15 września       |                                                                                                                                                                                               |
| Faktura 3     | 15 października  | 500.00 | 2% 14/ netto 30        | 29 października         |                                                                                                                                                                                               |
| Nota odsetkowa | 15 października  | 7,00   |                     |                    | Ta nota odsetkowa dotyczy faktur 1 i 2. Kwota wynosi 2% odsetek od kwot zaległych co najmniej 30 dni. Na przykład: 0,02 × (100,00 + 250,00) = 7,00. |

## <a name="user-defined-settlement-priority"></a>Priorytet rozliczania zdefiniowany przez użytkownika
Po ustawieniu opcji **Użyj priorytetu dla rozliczeń automatycznych** jako **Tak** na stronie **Parametry modułu rozrachunków z odbiorcami**, będzie używany priorytet rozliczenia zdefiniowany na stronie **priorytetu rozliczenia**, jeśli transakcje zostaną zaznaczone do automatycznego rozliczenia. W tym przykładzie zdefiniowano następujący priorytet rozliczenia:

1.  Typ transakcji
    -   Opłaty
    -   Ponaglenia
    -   Noty odsetkowe
    -   Faktury

2.  Data transakcji, Rosnąco
3.  Załącznik

Jeśli księgujesz płatność na kwotę 700,00 25 października, płatność jest rozliczana w transakcjach w następującej kolejności.

| Załącznik       | Data       | Faktura | Kwota w walucie transakcji | Kwota do rozliczenia | Saldo | Waluta |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Nota odsetkowa | 10/15/2015 |         | 7,00                           | 7,00             | 0,00    | USD      |
| Faktura 1     | 8/15/2015  | 10001   | 100,00                         | 100,00           | 0,00    | USD      |
| Faktura 2     | 9/1/2015   | 10002   | 250,00                         | 250,00           | 0,00    | USD      |
| Faktura 3     | 10/15/2015 |         | 500,00                         | 343,00           | 157,00  | USD      |

## <a name="default-automatic-settlement"></a>Domyślne automatyczne rozliczanie
W przypadku braku priorytetu rozliczenia zdefiniowanego przez użytkownika transakcje są automatycznie zaznaczane do rozliczenia na podstawie terminu. Transakcje, które są rozliczone, muszą mieć tę samą walutę co transakcje, którymi zostały rozliczone. Jeśli księgujesz płatność na kwotę 700,00 25 października, następujące transakcje są zaznaczone do rozliczenia.

| Załącznik       | Data       | Faktura | Kwota w walucie transakcji | Kwota do rozliczenia | Saldo | Waluta |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Faktura 1     | 8/15/2015  | 10001   | 100,00                         | 100,00           | 0,00    | USD      |
| Faktura 2     | 9/1/2015   | 10002   | 250,00                         | 250,00           | 0,00    | USD      |
| Faktura 3     | 10/15/2015 |         | 500.00                         | 350.00           | 150.00  | USD      |
| Nota odsetkowa | 10/15/2015 |         | 7.00                           | 0,00             | 7.00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
