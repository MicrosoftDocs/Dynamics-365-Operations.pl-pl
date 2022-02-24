---
title: Zwroty do odbiorców
description: W tym artykule wyjaśniono, jak tworzyć transakcje zwrotu nadpłaty dla grupy odbiorców. Jeśli odbiorca ma saldo dodatnie, można zwrócić mu wartość salda.
author: JodiChristiansen
manager: AnnBe
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65ee884fb22c1a38e2d3022085fed7e3e6077d1f
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644544"
---
# <a name="reimburse-customers"></a>Zwroty do odbiorców

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak tworzyć transakcje zwrotu nadpłaty dla grupy odbiorców. Jeśli odbiorca ma saldo dodatnie, można zwrócić mu wartość salda. 

W poniższej tabeli przedstawiono wymagania wstępne, które muszą istnieć przed rozpoczęciem.

| Wymaganie wstępne                                                            | Opis |
|-------------------------------------------------------------------------|-------------|
| Określanie minimalnej kwoty zwrotu pieniędzy dla firmy.          | Na stronie **Parametry modułu rozrachunków z odbiorcami** w obszarze **Ogólne** w polu **Minimalny zwrot** wprowadź minimalną kwotę, jaka może zostać zwrócony odbiorcy. |
| Opcjonalnie: Dodaj konto dostawcy do każdego odbiorcy, dla którego mogą zostać zwrócone nadpłaty | Na stronie **Odbiorcy** na skróconej karcie **Dodatkowe szczegóły** w polu **Konto dostawcy** wybierz konto dostawcy dla odbiorcy. |

Podczas tworzenia transakcji zwrotu, tworzona jest faktura od dostawcy na kwotę salda kredytu. Proces zwrotu nadpłaty usuwa saldo kredytu dla konta odbiorcy i tworzy saldo należne dla konta dostawcy, odpowiadającego odbiorcy.

1. W module Rozrachunki z odbiorcami uruchom proces **Zwrot nadpłaty** (**Rozrachunki z odbiorcami \> Zadania okresowe \> Zwrot nadpłaty**).
2. Aby grupować wszystkie transakcje, niezależnie od wymiarów księgowych, dla opcji **Sumuj odbiorcę** określ wartość **Tak**. Aby grupować tylko transakcje o podobnych wymiarach księgowych, ustaw w opcji wartość **Nie**.
3. Wybierz opcję **Uwzględnij odbiorców z zaległymi transakcjami debetowymi**, aby zaznaczyć odbiorców, którzy mają nierozliczone kwoty obciążeń.
4. Aby zwrócić nadpłaty na określone konta odbiorców, na skróconej karcie **Rekordy do uwzględnienia** kliknij opcję **Filtruj**, a następnie określ konta odbiorców w zapytaniu.

    Wartości kredytów są transferowane na konta dostawców odpowiedających odbiorcom i są przetwarzane jak zwykłe płatności. Jeśli odbiorca nie posiada konta dostawcy, zostanie automatycznie utworzone dla tego odbiorcy tymczasowe konto dostawcy.

5. Aby wyświetlić utworzone transakcje zwrotu nadpłaty, skorzystaj z raportu **Zwrot nadpłaty** (**Rozrachunki z odbiorcami \> Zapytania i raporty \> Raport Zwrot nadpłat**).
6. W module Rozrachunki z dostawcami należy utworzyć płatność dla faktur od dostawcy utworzonych w wyniku procesu zwrotu nadpłaty. Aby uzyskać informacje o sposobach płacenia dostawcom, zapoznaj się z tematem [Omówienie płatności dla dostawców](../accounts-payable/Vendor-payments-workspace.md).
