---
title: "Cofanie płatność dostawcy"
description: "W tym artykule opisano różnice między wycofywaniem, usuwaniem, unieważnianiem i odrzucaniem płatności. Ponadto objaśniono dwie metody wycofywania czeku dostawcy."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankChequeTable, LedgerJournalTransBankChequeReversal, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14361
ms.assetid: 9f0a1883-cbe0-4cc7-b9f3-dd12fb85ebe8
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4f8b77efabe0c002654dac0b80d721a79dc42003
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="reverse-a-vendor-payment"></a>Cofanie płatność dostawcy

[!include[banner](../includes/banner.md)]


W tym artykule opisano różnice między wycofywaniem, usuwaniem, unieważnianiem i odrzucaniem płatności. Ponadto objaśniono dwie metody wycofywania czeku dostawcy. 

Od czasu do czasu po zaksięgowaniu płatności na rzecz dostawcy płatność musi zostać wycofana. Wycofanie różni się od usuwania, unieważnienia lub odrzucania płatności. Płatność można usunąć tylko pod warunkiem, że ma stan **Utworzone**. Ten stan wskazuje, że płatność została utworzona, ale jeszcze nie została wygenerowana. To ograniczenie obowiązuje zawsze, niezależnie od metody płatności. Można unieważnić niezaksięgowane czeki po wygenerowaniu, ale przed zaksięgowaniem. Jeśli wygenerowana płatność zostanie zrealizowana jako przeniesienie środków elektronicznych (EFT), można ją odrzucić przed zaksięgowaniem. Aby odrzucić płatność, trzeba zmienić wartość **Stan płatności**. Płatność, która została unieważniona lub odrzucona, może zostać wygenerowana ponownie po zmianie wartości **Stan płatności** z powrotem na **Brak**. 

Jeśli płatność została zaksięgowana, trzeba zastosować wycofanie. Płatności zrealizowanych elektronicznie nie można wycofać po zaksięgowaniu. Zamiast tego trzeba utworzyć nową transakcję dla kwoty płatności, by ustawić zobowiązanie z powrotem na koncie dostawcy. Istnieją dwie metody wycofywania zaksięgowanych czeków. Według jednej metody cofnięcia są księgowane natychmiast po kliknięciu przycisku **Cofnięcie płatności** na stronie **Czek**. Według drugiej metody po kliknięciu opcji **Cofnięcie płatności** na stronie **Czek** cofnięcie jest przesyłane do arkusza cofania czeku w module Zarządzanie gotówką i bankami, gdzie osoba sprawdzająca może cofnięcie zaksięgować lub odrzucić. 

Aby sprawdzić, która metoda jest używana w danej organizacji, wyświetl stronę **Parametry zarządzania gotówką i bankami**. Jeśli opcja **Cofnij płatność w ramach procesu przeglądu** ma wartość **Tak**, cofnięcia są wysyłane do arkusza cofnięcia czeku do sprawdzenia. W poniższej tabeli opisano różnice pomiędzy metodami cofnięcia czeku.

| Jeśli organizacja nie przegląda cofnięć czeków przed zaksięgowaniem.                                                                                                                                  | Jeśli organizacja przegląda cofnięcia czeków przed zaksięgowaniem.                                                                                                                                                                                                                                                                                                                                                                     |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Czek jest wycofywany natychmiast po kliknięciu przycisku **OK** na stronie **Czek**.                                                                                                                      | Czek nie jest niezwłocznie wycofany. Arkusz wycofywania czeków jest tworzony do przeglądu. Po usunięciu arkusza wycofywania czeków, czek można ponownie wycofać.                                                                                                                                                                                                                                                                |
| Wpisy księgowe dla oryginalnego czeku zostaną wycofane.                                                                                                                                         | Konto księgowe z wpisu księgowania oryginalnego czeku nie może być zaksięgowane. Wymiary finansowe z arkusza oryginalnego czeku to domyślne wymiary finansowe w arkuszu wycofywania czeków. Można zmieniać takie wielkości domyślne. Po zaksięgowaniu arkusza cofnięcia czeku konta główne dla modułu Rozrachunki z dostawcami są wprowadzane automatycznie z profili księgowania, które mogły się zmienić. |
| Struktury księgowe, które zostały użyte podczas księgowania oryginalnego czeku służą do wycofania czeku, nawet jeśli zmieniono strukturę konta. Kombinacja konta nie jest sprawdzona. | Jeśli struktura konta uległa zmianie po zaksięgowaniu oryginalnego czeku, nowy wymiar finansowy może być wymagane w celu wycofania czeku. Ten wymiar finansowy nie może zostać wprowadzony automatycznie z arkusza oryginalnej płatności. Kombinacja konta jest sprawdzana pod kątem poprawności po zaksięgowaniu wycofania czeku.                                                                                                        |
| Stałe wymiary nie są stosowane do cofnięcia, by zapewnić, że wycofywane są te same konta księgowe.                                                                                      | Stałe wymiary są stosowane do arkusza wycofywania czeku podczas księgowania. Wartość wymiaru finansowego może nie istnieć w wpisie księgowym dla oryginalnego czeku, w zależności od tego, kiedy zdefiniowano stały wymiar.                                                                                                                                                                                                     |

## <a name="reverse-posted-checks-without-reviewing-them"></a>Wycofanie czeków zaksięgowanych bez przeglądania ich
Jeśli organizacja chce księgować cofnięcia czeków natychmiast po kliknięciu **Cofnięcie płatności** na stronie **Czeki**. Na stronie **Parametry zarządzania gotówką i bankami** ustaw opcję **Cofnij płatność w ramach procesu przeglądu** na **Nie**. Na stronie **Czeki** można wybrać czek do cofnięcia i wybrać **Cofnięcie płatności**. Następnie można wpisać datę i wybierz przyczynę cofnięcia.

## <a name="reverse-posted-checks-after-they-are-reviewed-in-the-check-reversal-journal"></a>Wycofanie czeków zaksięgowanych po przejrzeniu ich w arkuszu wycofywania czeków
Jeśli organizacja chce przejrzeć wycofania czeków przed ich zaksięgowaniem, utwórz arkusz cofania czeku do sprawdzenia i na stronie **Parametry zarządzania gotówką i bankami** ustaw opcję **Cofnij płatność w ramach procesu przeglądu** na **Tak**. Na stronie **Czeki** można wybrać czek do cofnięcia i wybrać **Cofnięcie płatności**. Następnie można wpisać datę i wybierz przyczynę cofnięcia. Należy również wybrać nazwę arkusza, aby utworzyć arkusz w arkuszu cofania czeku.

### <a name="review-a-reversal"></a>Sprawdzanie cofnięcia

Osoba, która dokonuje przeglądu cofnięć, może je zatwierdzić i zaksięgować w arkuszu lub odrzucić, usuwając arkusz. Na stronie **Arkusz cofnięcia czeku** można wybrać arkusz cofania do sprawdzenia, a następnie kliknąć przycisk **Wiersze**. Można sprawdzić cofnięty czek, a następnie wybrać jedną z następujących opcji zatwierdzania:

-   Aby zatwierdzić i zaksięgować arkusz cofania, kliknij **Księguj** lub **Zaksięguj i przenieś**.
-   Aby odrzucić cofnięcie, należy usunąć arkusz cofania czeku.

> [!NOTE]
> Usunięcie arkusza powoduje usunięcie wycofania z systemu, jednak oryginalny czek pozostaje na stronie **Czek**. Stanem czeku nie będzie już **Anulowanie oczekujące**.

## <a name="results-of-posting-a-reversal"></a>Wyniki zaksięgowania cofnięcia
Po zaksięgowaniu cofnięcia czeku ma miejsce następująca sytuacja:

-   Stan czeku jest zmieniany na **Anulowanie**.
-   Jeśli opcja **Uzgodnij** została wybrana na stronie cofania w trakcie cofania, czek jest uzgadniany (opcja **Uzgodniono** jest zaznaczona) i nie pojawia się na stronie **Uzgadnianie konta**.
-   Załącznik wyksięgowania jest księgowany na koncie bankowym, z którego wystawiono czek, aby zwiększyć saldo tego konta.
-   Załącznik jest księgowany w księdze głównej.
-   Szczegóły modyfikacji są aktualizowane w grupie pól **Historia** na stronie **Czek**.

> [!NOTE] 
> W wypadku wycofania czeku wystawionego w ramach międzyfirmowej transakcji handlowej, wpisy przeciwstawne wynikają z ustawień księgowania dla handlu międzyfirmowego, a nie z oryginalnej transakcji. Jeśli cofnięty czek wystawiono w związku z płatnością dla dostawcy, wówczas mają miejsce jeszcze następujące operacje:

-   Oryginalna płatność z faktury, z którą rozliczono tę płatność, nie zostaje zastosowana (rozliczenie zostaje wycofane).
-   Transakcja jest księgowana dla konta dostawcy w związku z cofnięciem płatności, a cofnięta płatność jest rozliczana z oryginalną płatnością. Wartość pola **Załącznik ostatniego rozliczenia** na stronie **Transakcje dostawcy** dotyczącej oryginalnej płatności dla dostawcy jest aktualizowana, tak aby wskazywała numer załącznika cofniętej transakcji.

Jeśli cofnięty czek został wystawiony w związku ze zwrotem pieniędzy dla odbiorcy, to dodatkowo mają miejsce następujące zdarzenia:

-   Transakcja jest księgowana dla konta odbiorcy w związku z cofnięciem płatności, a rozliczenie między oryginalną płatnością a dokumentem, dla którego była początkowo rozliczana płatność, jest wycofywane (jest tworzona płatność ujemna).
-   Cofnięcie płatności jest wprowadzane w odniesieniu do oryginalnej płatności. Wartość pola **Załącznik ostatniego rozliczenia** na stronie **Transakcje odbiorcy** dotyczącej oryginalnej płatności odbiorcy jest aktualizowana, tak aby wskazywała numer załącznika cofniętej transakcji.





