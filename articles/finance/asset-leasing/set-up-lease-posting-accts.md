---
title: Konfigurowanie kont księgowania wynajmu
description: W tym temacie wymieniono konta księgowania wymagane dla transakcji wynajmu składników majątku oraz objaśniono sposób definiowania kont księgowania na stronie Parametry księgowania wynajmu.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 147d8cd93f9664039b2004b878dcaff96c8b6ce6
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726386"
---
# <a name="set-up-lease-posting-accounts"></a>Konfigurowanie kont księgowania wynajmu

[!include [banner](../includes/banner.md)]

W tym temacie wymieniono konta księgowania wymagane dla transakcji wynajmu składników majątku oraz objaśniono sposób definiowania kont księgowania na stronie **Parametry księgowania wynajmu**.

Aby spełnić wymagania standardów Accounting Standards Codification Topic 842 (ASC 842) i Międzynarodowy Standard Sprawozdawczości Finansowej nr 16 (MSSF 16), może być konieczne utworzenie różnych kont w planie kont. Jednak konta tworzone zgodnie ze standardami ASC i MSSF nie są kontami środków trwałych. Na mocy regulacji ASC 842 składnik majątku z prawem do użytkowania (PDU) jest odnotowywany w transakcjach leasingu finansowego i operacyjnego. Te formy wynajmu są niezależne od środków trwałych. (Składnikiem majątku z PDU nadal można zarządzać za pomocą modułu Środki trwałe).

Aby uzyskać informacje na temat tworzenia struktur kont, zapoznaj się z tematem [Tworzenie struktur kont](../general-ledger/tasks/create-account-structures.md). Aby uzyskać informacje na temat tworzenia konta głównego, zapoznaj się z tematem [Tworzenie konta głównego](../general-ledger/tasks/create-main-account.md).

W poniższej tabeli przedstawiono przykłady kont, które należy utworzyć dla transakcji wynajętych składników majątku, jeśli nie zostały one jeszcze utworzone. Zgodnie z MSSF 16 umowy leasingu operacyjnego są nadal stosowane do wynajmu składników o niskiej wartości i na krótki okres.

| Numer konta księgowego | Typ konta  | Nazwa konta                                          |
|-----------------------|---------------|-------------------------------------------------------|
| 180150                | Element zawartości         | Składnik majątku z PDU: pojazd                                     |
| 180160                | Element zawartości         | Składnik majątku z PDU: budynek                                    |
| 180250                | Element zawartości         | Umorzenie — pojazdy                   |
| 180260                | Element zawartości         | Umorzenie — budynki                  |
| 222300                | Pasywa     | Zobowiązanie krótkoterminowe — umowy leasingu finansowego                |
| 222310                | Arkusz bilansowy | Zobowiązanie krótkoterminowe — umowy leasingu operacyjnego              |
| 250200                | Pasywa     | Noty naliczone                                         |
| 250601                | Arkusz bilansowy | Zobowiązanie długoterminowe — umowy leasingu finansowego                 |
| 250602                | Arkusz bilansowy | Zobowiązanie długoterminowe — umowy leasingu operacyjnego               |
| 250606                | Arkusz bilansowy | Odroczony czynsz                                         |
| 300160                | Arkusz bilansowy | Wstrzymane dochody                                     |
| 604500                | Expense       | Wydatek z tytułu wynajmu                                         |
| 604501                | Expense       | Wydatek z tytułu leasingu operacyjnego pojazdu — naliczanie odsetek  |
| 604502                | Expense       | Wydatek z tytułu leasingu operacyjnego pojazdu — amortyzacja        |
| 605200                | Expense       | Wydatek z tytułu leasingu operacyjnego budynku — naliczanie odsetek |
| 605201                | Expense       | Wydatek z tytułu leasingu operacyjnego budynku — amortyzacja       |
| 607101                | Expense       | Wydatek z tytułu amortyzacji wynajmu pojazdu                    |
| 607102                | Expense       | Wydatek z tytułu amortyzacji wynajmu budynku                   |
| 607103                | Expense       | Wydatek utraty wartości — umowy leasingu finansowego                   |
| 607104                | Expense       | Wydatek utraty wartości — umowy leasingu operacyjnego                 |
| 618910                | Expense       | Wydatek z tytułu wynajmu — umowy leasingu finansowego                        |
| 618920                | Expense       | Opłaty zmienne — umowy leasingu finansowego                    |
| 618930                | Expense       | Opłaty zmienne — umowy leasingu operacyjnego                  |
| 800600                | Expense       | Koszty odsetek z tytułu wynajmu pojazdu                        |
| 800601                | Expense       | Koszty odsetek z tytułu wynajmu budynku                       |
| 801201                | Arkusz bilansowy | Zysk i strata — modyfikacja wynajmu                      |

## <a name="configure-posting-accounts"></a>Konfigurowanie kont księgowania

Aby przypisać konta do utworzonych ksiąg i grup wynajmu, należy skonfigurować parametry wynajmu składnika majątku.

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Parametry księgowania wynajmu**.
2. Na karcie **Konta** otwórz skróconą kartę **Konta wynajmu**. Określ główne konta dla umów leasingu finansowego i operacyjnego odpowiadające parametrowi **Typ księgowania**. Wcześniejsza tabela przedstawia konta, które są związane z umowami leasingu operacyjnego i finansowego.

    > [!NOTE]
    > Ten krok wymaga skonfigurowania osobnych kont dla umów leasingu operacyjnego i finansowego dla każdego typu księgowania poza **Kompensacja wydatku z tytułu wynajmu** i **Zwiększenie/zmniejszenie wartości przedmiotu wynajmu**. Firmy stosujące strukturę księgową określoną w standardzie MSSF 16 muszą dodać konto główne dla leasingu operacyjnego. Jednak system nie będzie używał tego konta, mimo że jest to pole wymagane, ponieważ zgodnie z MSSF 16 wszystkie umowy wynajmu są klasyfikowane jako leasing finansowy.
    >[!NOTE]
    > Parametr **Zwiększenie/zmniejszenie wartości przedmiotu wynajmu** będzie używany jako typ księgowania dla dodatkowych aspektów składnika majątku, w tym **Początkowy koszt bezpośredni, Prowizje stymulujące wynajem, Przedpłaty za wynajem i Koszty demontażu**, ale księgowane będzie dokonywane na koncie głównym składnika majątku z prawem do użytkowania, którym domyślnie jest **Należność z tytułu wynajmu**.        
    
3. Aby wybrać określoną grupę wynajmu odpowiadającą kontu głównemu, w polu **Kod konta** wybierz opcję **Grupa**. Następnie w polu **Numer konta/grupy** wybierz grupę wynajmu, która ma zostać przypisana do konta głównego.
4. Aby przypisać kody kont do kosztów administracyjnych skonfigurowanych w systemie, na skróconej karcie **Koszty wykonawcze** w polu **Typ wydatku** wybierz wydatek. Następnie przypisz konta finansowe i operacyjne, które mają być używane dla każdej księgi.

    > [!NOTE]
    > Wybrane konto finansowe lub operacyjne będzie obciążane podczas księgowania faktury za zaplanowany wydatek.
    > Parametr **Kompensacja wydatku z tytułu wynajmu** będzie używany jako typ księgowania dla transakcji na kosztach wykonawczych, ale księgowanie będzie dokonywane na koncie zdefiniowanym w polu **Konto przeciwstawne** w oknie **Wiersze harmonogramu płatności kosztów wykonawczych** w szczegółach wynajmu lub formularzu księgi wynajmu.   


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
