---
title: "Zwroty do odbiorców"
description: "W tym artykule wyjaśniono, jak tworzyć transakcje zwrotu nadpłaty dla grupy odbiorców. Jeśli odbiorca ma saldo dodatnie, można zwrócić mu wartość salda."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 01c9dcebe82544624c6dd0feb3672d1c5bdfe2d1
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="reimburse-customers"></a>Zwroty do odbiorców

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak tworzyć transakcje zwrotu nadpłaty dla grupy odbiorców. Jeśli odbiorca ma saldo dodatnie, można zwrócić mu wartość salda. 

W poniższej tabeli przedstawiono wymagania wstępne, które muszą istnieć przed rozpoczęciem.

| Wymaganie wstępne                                                            | Opis                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Określanie minimalnej kwoty zwrotu pieniędzy dla firmy.          | Na stronie **Parametry modułu rozrachunków z odbiorcami** w obszarze **Ogólne** w polu **Minimalny zwrot** wprowadź minimalną kwotę, jaka może zostać zwrócony odbiorcy. |
| Opcjonalnie: Dodaj konto dostawcy do każdego odbiorcy, dla którego mogą zostać zwrócone nadpłaty | Na stronie **Odbiorcy** na skróconej karcie **Dodatkowe szczegóły** w polu **Konto dostawcy** wybierz konto dostawcy dla odbiorcy.                                           |

Podczas tworzenia transakcji zwrotu, tworzona jest faktura od dostawcy na kwotę salda kredytu. Proces zwrotu nadpłaty usuwa saldo kredytu dla konta odbiorcy i tworzy saldo należne dla konta dostawcy, odpowiadającego odbiorcy.

1.  W module Rozrachunki z odbiorcami uruchom proces **Zwrot nadpłaty**.
2.  Wykonaj jeden z następujących kroków:
    -   Aby dokonać zwrotu nadpłaty na określone konta, należy kliknąć opcję **Wybierz** i wprowadzić w kwerendzie właściwe konta odbiorcy.
    -   Aby dokonać zwrotu nadpłaty na wszystkie konta, należy kliknąć przycisk **OK**.

    Wartości kredytów są transferowane na konta dostawców odpowiedających odbiorcom i są przetwarzane jak zwykłe płatności. Jeśli odbiorca nie posiada konta dostawcy, zostanie automatycznie utworzone dla tego odbiorcy tymczasowe konto dostawcy.
3.  Aby wyświetlić utworzone transakcje zwrotu nadpłaty, użyj strony **Zwrot nadpłaty**.
4.  W module Rozrachunki z dostawcami należy utworzyć płatność dla faktur od dostawcy utworzonych w wyniku procesu zwrotu nadpłaty.





