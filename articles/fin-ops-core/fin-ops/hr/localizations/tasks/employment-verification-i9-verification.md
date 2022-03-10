---
title: Weryfikacja zatrudnienia weryfikacja i9
description: Zgodnie z Ustawą o reformie przepisów imigracyjnych i kontroli imigracji (IRCA) pracodawcy w Stanach Zjednoczonych muszą sprawdzać, czy nowo zatrudniani przez nich pracownicy mają odpowiednie zezwolenie na pracę.
author: ShielaSogge
ms.date: 01/10/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, HcmPersonIdentificationNumber, Hcmi9Document
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b76102111a8506882f2301d76856ae1a34a7c704
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065688"
---
# <a name="employment-verification-i9-verification"></a>Weryfikacja zatrudnienia weryfikacja i9

[!include [banner](../../../includes/banner.md)]


[!INCLUDE [PEAP](../../../../../includes/peap-1.md)]

Zgodnie z Ustawą o reformie przepisów imigracyjnych i kontroli imigracji (IRCA) pracodawcy w Stanach Zjednoczonych muszą sprawdzać, czy nowo zatrudniani przez nich pracownicy mają odpowiednie zezwolenie na pracę. Ta procedura prowadzi przez kolejne kroki rejestrowania niezbędnych dokumentów w celu weryfikacji zawartości formularza I-9. Procedura wykorzystuje firmę demonstracyjną USMF.

1. Wybierz kolejno opcje **Zasoby ludzkie \> Pracownicy \> Pracownicy**.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj z wartością **Vince** według pola **Nazwa**.
3. Zaznacz pracownika. Na przykład wybierz wartość **Vince Prado**.
4. Rozwiń skróconą kartę **Informacje osobiste**.
5. Wybierz **Numer identyfikacyjny osoby**.
6. Wybierz pozycję **Nowy**.
7. Zaznacz typ rejestrowanego identyfikatora. Na przykład wybierz wartość **Paszport**.
8. W polu **Numer** wprowadź liczbę.
9. W polu **podstawowe** wybierz opcję **tak**.
10. W polu **Opis** wprowadź krótki opis rekordu identyfikacyjnego.
11. W polu **Agencja wystawiająca** zaznacz agencję, która wydała pracownikowi dokument identyfikacyjny. Na przykład wybierz wartość **Rząd**.
12. Wprowadź datę, kiedy agencja wystawiła pracownikowi dokument identyfikacyjny. Na przykład wpisz datę **15-02-2021** (15 luty 2011).
13. Wprowadź datę, kiedy dokument identyfikacyjny wygasa. Na przykład wpisz datę **15-02-2021** (15 luty 2021).
14. Wybierz opcję **Zapisz**.
15. Zamknij stronę.
16. Kliknij kartę **Zatrudnienie**.
17. Zaznacz **I-9**.
18. Wybierz pozycję **Nowy**.
19. W polu **Uprawnienie do pracy** wybierz opcję.

    Jeśli pracownik nie jest obywatelem lub mieszkańcem Stanów Zjednoczonych, należy wprowadzić numer jego zezwolenia lub dokumentu obcokrajowca.

20. Wybierz opcję **GroupListA**.

    Wybrana lista zależy od tego, jaką formę identyfikacji dostarczył pracownik. Pracownik musi dostarczyć jeden dokument z Listy A lub jeden dokument z Listy B i Listy C. Na przykład, jeśli pracownik dostarczył paszport, możesz wybrać Listę A. Jeśli jednak pracownik dostarczył tylko prawo jazdy i ubezpieczenie społeczne kartę, musisz wybrać Listę B i Listę C.

21. W polu **Typ dokumentów I-9** zaznacz typ dokumentu dostarczonego przez pracownika.
22. W polu **Numer dokumentu** wprowadź lub wybierz wartość.
23. Wybierz opcję **Zapisz**.

[!INCLUDE[footer-include](../../../../../includes/footer-banner.md)]
