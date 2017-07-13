---
title: Automatyczne rozliczanie i priorytety
description: "W tym artykule opisano, jak transakcje są rozliczane po wybraniu opcji Automatyczne rozliczanie na stronie Parametry modułu rozrachunków z odbiorcami. Wyjaśniono również możliwości używania automatycznego rozliczania w połączeniu z priorytetem płatności."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14531
ms.assetid: e7837cf6-ec69-44b4-8d47-eba38d5c7b1f
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 3e2ca11eef4246d5abfd77351325ac2b4440b446
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# Automatyczne rozliczanie i priorytety
<a id="automatic-settlement-and-prioritization" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W tym artykule opisano, jak transakcje są rozliczane po wybraniu opcji Automatyczne rozliczanie na stronie Parametry modułu rozrachunków z odbiorcami. Wyjaśniono również możliwości używania automatycznego rozliczania w połączeniu z priorytetem płatności.

Dostępne są dwie opcje rozliczania płatności za pomocą faktur i innych transakcji. Można ręcznie wybrać transakcje do rozliczenia lub program Microsoft Dynamics 365 for Finance and Operations może wybrać transakcje automatycznie za pomocą funkcji automatycznego rozliczania. Można także dostosować sposób przetwarzania automatycznych rozliczeń przy użyciu opcji **Określanie priorytetów rozliczenia**. Wszystkie te opcje są częścią parametrów rozliczenia określanych na stronie **Parametry modułu rozrachunków z odbiorcami**. Sposób automatycznego rozliczania transakcji może się różnić w zależności od używanej metody automatycznego rozliczania. Dostępne są następujące metody:

-   Priorytet rozliczania zdefiniowany przez użytkownika
-   Domyślne automatyczne rozliczanie

W poniższych sekcjach opisano sposób rozliczania transakcji w przypadku każdej z metod.

## Przykładowe transakcje
<a id="example-transactions" class="xliff"></a>
Przykłady rozliczeń w dalszej części tego artykułu są oparte na następujących transakcjach. Wszystkie transakcje dotyczą odbiorcy 2050.

| Transakcja   | Data        | Kwota | Warunki rabatu gotówkowego | Data rabatu gotówkowego | Komentarze                                                                                                                                                                                      |
|---------------|-------------|--------|---------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Faktura 1     | 15 sierpnia   | 100,00 | 2%14, netto 30        | 29 sierpnia          |                                                                                                                                                                                               |
| Faktura 2     | 1 września | 250,00 | 2%14, netto 30        | 15 września       |                                                                                                                                                                                               |
| Faktura 3     | 15 października  | 500,00 | 2%14/ netto 30        | 29 października         |                                                                                                                                                                                               |
| Nota odsetkowa | 15 października  | 7,00   |                     |                    | Ta nota odsetkowa dotyczy faktur 1 i 2. Kwota wynosi 2% odsetek od kwot zaległych co najmniej 30 dni. Na przykład: 0,02 × (100,00 + 250,00) = 7,00. |

## Priorytet rozliczania zdefiniowany przez użytkownika
<a id="userdefined-settlement-priority" class="xliff"></a>
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

## Domyślne automatyczne rozliczanie
<a id="default-automatic-settlement" class="xliff"></a>
W przypadku braku priorytetu rozliczenia zdefiniowanego przez użytkownika transakcje są automatycznie zaznaczane do rozliczenia na podstawie terminu. Transakcje, które są rozliczone, muszą mieć tę samą walutę co transakcje, którymi zostały rozliczone. Jeśli księgujesz płatność na kwotę 700,00 25 października, następujące transakcje są zaznaczone do rozliczenia.

| Załącznik       | Data       | Faktura | Kwota w walucie transakcji | Kwota do rozliczenia | Saldo | Waluta |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Faktura 1     | 8/15/2015  | 10001   | 100,00                         | 100,00           | 0,00    | USD      |
| Faktura 2     | 9/1/2015   | 10002   | 250,00                         | 250,00           | 0,00    | USD      |
| Faktura 3     | 10/15/2015 |         | 500,00                         | 350,00           | 150,00  | USD      |
| Nota odsetkowa | 10/15/2015 |         | 7,00                           | 0,00             | 0,00    | USD      |






