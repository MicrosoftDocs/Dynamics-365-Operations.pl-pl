--- 
title: "Generowanie raportów w formacie pakietu Microsoft Office z osadzonymi obrazami na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik odtwarzający rolę „Administrator systemu” lub „Deweloper raportowania elektronicznego” może projektować konfiguracje raportowania elektronicznego (ER) w celu generowania dokumentów elektronicznych w formatach dokumentów pakietu MS Office (Excel i Word) zawierających osadzone obrazy."
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
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
ms.openlocfilehash: 4576d89923926971ab3ca30dc702baedf05f602a
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="generate-reports-in-microsoft-office-formats-with-embedded-images-for-electronic-reporting-er"></a>Generowanie raportów w formacie pakietu Microsoft Office z osadzonymi obrazami na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik odtwarzający rolę „Administrator systemu” lub „Deweloper raportowania elektronicznego” może projektować konfiguracje raportowania elektronicznego (ER) w celu generowania dokumentów elektronicznych w formatach dokumentów pakietu MS Office (Excel i Word) zawierających osadzone obrazy.

W tym przykładzie użyjesz utworzonych konfiguracji ER dla przykładowej firmy „Litware, Inc.”.  Aby wykonać te kroki, należy najpierw wykonać kroki z przewodnika po zadaniu „ER Tworzenie raportów w formatach programu MS Office z osadzonymi obrazami (Część 2: Przegląd konfiguracji)”. Kroki można wykonać na danych firmy „USMF”.


## <a name="run-format-with-initial-model-mapping"></a>Uruchamianie formatu z początkowym mapowaniem modelu
1. Kliknij kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe > Konta bankowe.
2. Użyj szybkiego filtru, aby wyfiltrować pole Konto bankowe według wartości „USMF OPER”.
3. W okienku akcji kliknij pozycję Konfiguracja.
4. Kliknij przycisk Sprawdź.
5. Kliknij opcję Drukowanie testu.
    * Uruchom format do celów testowych.  
6. W polu Format czeku zbywalnego wybierz opcję Tak.
7. Kliknij przycisk OK.
    * Przejrzyj produkt wyjściowy. Należy zauważyć, że w raporcie jest przedstawiane logo firmy oraz podpis osoby upoważnionej. Obraz podpisu jest pobierany z pola danych typu „Kontener” w rekordzie układu czeku skojarzonym z wybranym kontem bankowym.  
8. Rozwiń sekcję Kopie.
9. Kliknij przycisk Edytuj.
10. W polu Znak wodny wprowadź tekst „Drukuj znak wodny jako unieważniony”.
    * Zmień ustawienie znaku wodnego, aby był pokazywany tekst znaku wodnego podczas generowania dokumentu w elemencie kształtu programu Excel.  
11. Kliknij opcję Drukowanie testu.
12. Kliknij przycisk OK.
    * Przejrzyj produkt wyjściowy. Należy zauważyć, że znak wodny jest widoczny w utworzonym raporcie zgodnie z wybraną opcją.  
13. Zamknij stronę.
14. W okienku akcji kliknij pozycję Zarządzanie płatnościami.
15. Kliknij przycisk Czeki.
16. Kliknij przycisk Pokaż filtry.
17. Zastosuj następujące filtry: wprowadź wartość filtru „381”,„385”,„389” w polu „Numer czeku”, stosując operator filtru „jest jednym z”.
18. Na liście zaznacz wszystkie wiersze.
19. Kliknij opcję Drukuj kopię czeku.
    * Uruchom format, aby ponownie wydrukować wybrane czeki.  
    * Przejrzyj produkt wyjściowy. Należy zauważyć, że wybrane czeki zostały ponownie wydrukowane. Logo firmy i etykiety nie są drukowane, ponieważ znajdują się na formularzu z nadrukiem.  

## <a name="modify-the-mapping-of-the-imported-data-model"></a>Modyfikowanie mapowania zaimportowanego modelu danych
1. Zamknij stronę.
2. Zamknij stronę.
3. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
4. W drzewie zaznacz element „Model czeków”.
5. Kliknij przycisk Konstruktor.
6. Kliknij opcję Mapuj model na źródło danych.
7. Kliknij przycisk Konstruktor.
    * Zmienimy powiązanie elementu podpisu modelu danych, tak aby obraz podpisu był pobierany z pliku dołączonego do rekordu układu czeku skojarzonego z wybranym kontem bankowym.  
8. Wyłącz opcję Pokaż szczegóły.
9. W drzewie rozwiń węzeł „układ”.
10. W drzewie rozwiń węzeł „układ\podpis”.
11. W drzewie zaznacz element „układ\podpis\obraz = chequesaccount.'<Relacje'.BankChequeLayout.Signature1Bmp”.
12. W drzewie rozwiń węzeł „chequesaccount”.
13. W drzewie rozwiń węzeł „chequesaccount\<Relacje”.
14. W drzewie rozwiń węzeł „chequesaccount\<Relacje\BankChequeLayout”.
15. W drzewie rozwiń węzeł „chequesaccount\<Relacje\BankChequeLayout\<Relacje”.
16. W drzewie rozwiń węzeł „chequesaccount\<Relacje\BankChequeLayout\<Relacje\<Dokumenty”.
17. W drzewie zaznacz element „chequesaccount\<Relacje\BankChequeLayout\<Relacje\<Dokumenty\getFileContentAsContainer()”.
18. Kliknij opcję Powiąż.
19. Kliknij przycisk Zapisz.
20. Zamknij stronę.
21. Zamknij stronę.
22. Zamknij stronę.
23. Zamknij stronę.

## <a name="run-format-using-the-adjusted-model-mapping"></a>Uruchamianie formatu przy użyciu skorygowanego mapowania modelu
1. Kliknij kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe > Konta bankowe.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Konto bankowe z wartością „USMF OPER”.
3. W okienku akcji kliknij pozycję Konfiguracja.
4. Kliknij przycisk Sprawdź.
5. Kliknij opcję Drukowanie testu.
6. Kliknij przycisk OK.
    * Przejrzyj produkt wyjściowy. Należy zauważyć, że obraz z załącznika funkcji zarządzania dokumentami jest wyświetlany jako podpis osoby upoważnionej.  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a>Używanie dokumentu programu Microsoft Word jako szablonu w zaimportowanym formacie
1. Zamknij stronę.
2. Zamknij stronę.
3. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
4. W drzewie rozwiń węzeł „Model czeków”.
5. W drzewie zaznacz element „Model czeków\Format drukowania czeków”.
6. Kliknij przycisk Konstruktor.
7. Kliknij opcję Załączniki.
8. Kliknij przycisk Usuń.
9. Kliknij przycisk Tak.
10. Kliknij przycisk Nowy.
11. Kliknij opcję Plik.
    * Kliknij przycisk Przeglądaj i zaznacz pobrany wcześniej plik „Cheque template Word.docx”.  
12. Zamknij stronę.
13. W polu Szablon wprowadź lub wybierz wartość.
14. Kliknij przycisk Zapisz.
15. Zamknij stronę.
16. Kliknij przycisk Edytuj.
17. W polu Uruchom wersję roboczą wybierz opcję Tak.
18. Zamknij stronę.
19. Kliknij kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe > Konta bankowe.
20. Użyj szybkiego filtru, aby wyfiltrować pole Konto bankowe według wartości „USMF OPER”.
21. Kliknij przycisk Sprawdź.
22. Kliknij opcję Drukowanie testu.
23. Kliknij przycisk OK.
    * Przejrzyj produkt wyjściowy. Należy zwrócić uwagę, że dane wyjściowe zostały wygenerowane jako dokument programu Microsoft Word z osadzonymi obrazami prezentującymi logo firmy, podpis osoby upoważnionej i wybrany tekst znaku wodnego.  


