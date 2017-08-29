--- 
title: "Uruchamianie formatu w celu używania plików zarządzania dokumentami w danych wyjściowych formatu na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników)."
author: NickSelin
manager: AnnBe
ms.date: 10/31/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 6e1d7a54055829a1e9215a44f8eba346291f6717
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="run-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a>Uruchamianie formatu w celu używania plików zarządzania dokumentami w danych wyjściowych formatu na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników). Kroki można wykonać na danych firmy DEMF.

W celu wykonania tych kroków należy najpierw wykonać kroki procedury „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 3: Tworzenie formatu)”.

Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a>Dodawanie niezbędnych załączników dla zamówienia sprzedaży z jedną fakturą
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Otwarte faktury odbiorcy.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Faktura z wartością „CIV-000148”.
    * CIV-000148  
3. Kliknij, aby otworzyć łącze do wybranej faktury.
    * CIV-000148  
4. Kliknij, aby otworzyć łącze istniejące w polu Zamówienie sprzedaży.
    * 000148  
5. W polu Wiersze lub nagłówek wybierz opcję Nagłówek.
    * Wybierz opcję Nagłówek, aby wskazać, że będzie to docelowe miejsce dodawania załączników.  
6. Kliknij opcję Dołącz.
    * Dodaj kilka plików jako załączniki do tego zamówienia sprzedaży. Użyj plików dokumentów o typach obsługiwanych w zarządzaniu dokumentami (z rozszerzeniem DOCX, DPF, XML, JPG itp.). Znajdź i zaznacz pliki, które mają zostać dołączone i być dalej przetwarzane z powiązaną fakturą w komunikacie elektronicznym raportowania elektronicznego.  
7. Kliknij przycisk Nowy.
8. Kliknij opcję Plik.
9. Kliknij przycisk Nowy.
10. Kliknij opcję Plik.
11. Zamknij stronę.
12. Zamknij stronę.
13. Zamknij stronę.
14. Zamknij stronę.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>Generowanie zaprojektowanego raportu dla wybranej faktury
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie rozwiń węzeł „Model faktur sprzedaży”.
3. W drzewie rozwiń węzeł „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.
4. W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)\Przykładowy komunikat faktury elektronicznej”.
5. Kliknij przycisk Uruchom.
6. Rozwiń sekcję Rekordy do uwzględnienia ().
7. Kliknij przycisk Filtr.
8. Zaznacz wiersz z arkuszem faktur dla odbiorcy i polem Zamówienie sprzedaży.
9. W polu Kryteria wpisz wartość „000148”.
    * W polu kryteriów „Zamówienie sprzedaży” wpisz numer zamówienia 000148.  
10. Kliknij przycisk OK.
11. Kliknij przycisk OK.
    * Przejrzyj wygenerowane dane wyjściowe. Należy zauważyć, że dla każdego załącznika został utworzony jeden węzeł XML. Treść załączników zostanie zapisana w danych wyjściowych XML w formacie tekstowym MIME (base64).  


