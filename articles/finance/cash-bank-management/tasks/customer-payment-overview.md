---
title: Omówienie płatności odbiorców
description: W tej procedurze omówiono różne metody służące do wprowadzania płatności od odbiorców.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, CustPaymEntry, CustTableLookup, LedgerJournalTransCustPaym, CustOpenTrans, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7b90b7f200133cfb0d30b335aca20c328856fba5
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778130"
---
# <a name="customer-payment-overview"></a>Omówienie płatności odbiorców

[!include [banner](../../includes/banner.md)]

W tej procedurze omówiono różne metody służące do wprowadzania płatności od odbiorców. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Płatności > Arkusz płatności**.
2. Kliknij przycisk **Nowy**.
3. Wybierz arkusz płatności, w którym mają być zapisywane płatności od odbiorcy.
4. Wybierz arkusz lub wprowadź go ręcznie.
5. W **okienku akcji** kliknij pozycję **Wprowadzanie płatności odbiorcy**. Formularz Wprowadzanie płatności odbiorcy jest używany do rejestrowania jednej płatności od odbiorcy w danej chwili. Informacje o płatności wprowadza się u góry. Następnie można oznaczyć faktury, które zostały zapłacone za pomocą płatności, wszystkie na tej samej stronie.  
6. Wprowadź odbiorcę, od którego otrzymano płatność. Jeśli nie znasz odbiorcy, ale znasz transakcję, która została zapłacona, możesz użyć pola **Transakcja**, aby wprowadzić płatność. Wprowadź lub wybierz transakcję w polu **Transakcja**. Odbiorca zostanie ustawiony automatycznie po wybraniu transakcji.
7. W polu **Odwołanie do płatności** wprowadź odwołanie do płatności. Odwołaniem do płatności może być numer czeku odbiorcy lub odwołanie z płatności elektronicznej odbiorcy. Odwołanie do płatności jest wymagane tylko wtedy, jeśli płatność oznaczono do uwzględnienia na dokumencie wpłaty.  
8. W poli **Dokument wpłaty** określ, czy płatność będzie uwzględniona na dokumencie wpłaty. 
9. W polu **Kwota** wprowadź kwotę płatności odbiorcy. Kwota płatności nie jest wprowadzana domyślnie. Należy ją wpisać ręcznie. 
10. Oznacz faktury, które zostały zapłacone przez odbiorcę. Jeśli płatność jest zaliczką, nie trzeba oznaczać żadnych faktur do rozliczenia. Płatność można nadal zapisać i zaksięgować. Rozliczenie faktury może nastąpić w późniejszym czasie.
11. Wprowadź kwotę płatności, która ma zostać rozliczona względem oznaczonej faktury. Tego pola można używać w przypadku regulowania płatności częściowej. Jeśli nie wprowadzisz kwoty, kwota do rozliczenia zostanie ustalona automatycznie.
12. Kliknij opcję **Zapisz w arkuszu**. Przed zapisaniem płatności do arkusza upewnij się, że jest zdefiniowane konto przeciwstawne. Opcja **Zapisz w arkuszu** spowoduje zapisanie płatności i przeniesienie jej do arkusza. Wtedy można kontynuować wprowadzanie następnej płatności.
13. Zamknij stronę.
14. W **Panelu akcji** kliknij **Linie**. Podczas otwierania **Wierszy** będzie widać wszystkie płatności zarejestrowane na stronie **Wprowadzanie płatności odbiorcy** i zapisane w arkuszu. Ta strona umożliwia również wprowadzanie nowych płatności od odbiorcy lub edytowanie istniejących płatności od odbiorcy przed ich zaksięgowaniem.
15. Kliknij przycisk **Nowy**, aby utworzyć kolejną płatność. 
16. Wybierz odbiorcę, od którego otrzymano płatność. Jeśli odbiorca nie jest znany, ale znasz fakturę regulowaną przez płatność, wypełnij pole **Faktura** ręcznie lub wybierz fakturę. Po wybraniu faktury odbiorca zostanie określony domyślnie.  
17. Kliknij opcję **Rozlicz transakcje**, aby oznaczyć faktury, które zostały zapłacone. Nie musisz rozliczać płatności względem jakiejkolwiek faktury. Jeśli płatność jest zaliczką lub jeśli nie wiesz, która faktura została zapłacona, możesz wprowadzić i zaksięgować samą płatność. Może ona zostać rozliczona względem faktury w późniejszym czasie.  
18. Oznacz faktury zapłacone za pomocą płatności. 
19. W polu **Kwota** wprowadź kwotę płatności, która zostanie rozliczona względem faktury.
20. Kliknij przycisk **OK**.
21. W polu **Odwołanie do płatności** wprowadź odwołanie do płatności. Odwołanie do płatności jest wymagane tylko wtedy, jeśli płatność oznaczono do uwzględnienia na dokumencie wpłaty.  
22. W **okienku akcji** kliknij przycisk **Księguj**, aby zaksięgować fakturę dla odbiorcy. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
