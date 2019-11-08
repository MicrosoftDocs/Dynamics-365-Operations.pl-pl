---
title: ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 3 — tworzenie formatu)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego, aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 618fabc96bdfeb0c2b577aa686702d9f1257ed70
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550724"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a>ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 3 — tworzenie formatu)

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników). Kroki można wykonać na danych dowolnej firmy.

W celu wykonania tych kroków należy najpierw wykonać kroki procedury „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 2: Rozszerzanie modelu danych)”.

Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.


## <a name="create-a-format-to-process-invoices"></a>Tworzenie formatu przetwarzania faktur
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Konfiguracje raportowania.
3. W drzewie rozwiń węzeł „Model faktur sprzedaży”.
4. W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.
    * Utworzysz format do generowania komunikatów elektronicznych z informacjami o wszystkich plikach, które zostały dołączone do zamówienia sprzedaży powiązanego z elektronicznie przetworzoną fakturą.  
5. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
6. W polu Nowy wpisz „Format oparty na modelu danych Model faktur sprzedaży (niestandardowy)”.
7. W polu Nazwa wpisz „Przykładowy komunikat faktury elektronicznej”.
    * Przykładowy komunikat faktury elektronicznej  
8. W polu Definicja modelu danych wprowadź lub wybierz wartość.
    * InvoiceCustomer  
9. Kliknij przycisk Utwórz konfigurację.

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a>Projektowanie formatu w celu dodania do generowanego komunikatu treści załączników w formacie MIME
1. Kliknij przycisk Konstruktor.
2. Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.
3. W drzewie zaznacz element „XML\Element”.
4. W polu Nazwa wpisz „Faktura”.
    * Faktura VAT  
5. Kliknij przycisk OK.
6. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
7. W drzewie zaznacz element „XML\Atrybut”.
8. W polu Nazwa wpisz „SalesOrder”.
    * SalesOrder  
9. Kliknij przycisk OK.
10. Kliknij opcję Dodaj atrybut.
11. W polu Nazwa wpisz „InvoiceNumber”.
    * InvoiceNumber  
12. Kliknij przycisk OK.
13. Kliknij opcję Dodaj atrybut.
14. W polu Nazwa wpisz „InvoiceAmount”.
    * InvoiceAmount  
15. Kliknij przycisk OK.
16. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
17. W drzewie zaznacz element „XML\Element”.
18. W polu Nazwa wpisz „EnclosedDocs”.
    * EnclosedDocs  
19. Kliknij przycisk OK.
20. W drzewie zaznacz element „Faktura\EnclosedDocs”.
21. Kliknij opcję Dodaj element.
22. W polu Nazwa wpisz „Dokument”.
    * Wydruk pokwitowania  
23. Kliknij przycisk OK.
24. W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument”.
25. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
26. W drzewie zaznacz element „XML\Atrybut”.
27. W polu Nazwa wpisz „FileName”.
    * Nazwa pliku  
28. Kliknij przycisk OK.
29. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
30. W drzewie zaznacz element „XML\Element”.
31. W polu Nazwa wpisz „FileContent”.
    * FileContent  
32. Kliknij przycisk OK.
33. W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument\FileContent”.
34. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
35. W drzewie zaznacz element „Tekst\Base64”.
36. Kliknij przycisk OK.

## <a name="map-format-elements-to-data-model-as-data-source"></a>Mapowanie elementów formatu na model danych jako źródło danych
1. W drzewie zaznacz element „Faktura\SalesOrder”.
2. Kliknij kartę Mapowanie.
3. W drzewie rozwiń model„”
4. W drzewie zaznacz element „model\Numer zamówienia sprzedaży(SalesId)”.
5. Kliknij opcję Powiąż.
6. W drzewie zaznacz element „Faktura\InvoiceNumber”.
7. W drzewie rozwiń węzeł „model\Faktura podstawowa(InvoiceBase)”.
8. W drzewie zaznacz element „model\Faktura podstawowa(InvoiceBase)\Numer faktury(Identyfikator)”.
9. Kliknij opcję Powiąż.
10. W drzewie zaznacz element „Faktura\InvoiceAmount”.
11. W drzewie zaznacz element „model\Faktura podstawowa(InvoiceBase)\Kwota faktury(Kwota)”.
12. Kliknij opcję Powiąż.
13. W drzewie rozwiń węzeł „model\Załączniki faktur”.
14. W drzewie zaznacz element „model\Załączniki faktur\Zawartość pliku”.
15. W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument\FileContent\Base64”.
16. Kliknij opcję Powiąż.
17. W drzewie zaznacz element „model\Załączniki faktur\Nazwa pliku”.
18. W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument\FileName”.
19. Kliknij opcję Powiąż.
20. W drzewie zaznacz element „model\Załączniki faktur”.
21. W drzewie zaznacz element „Faktura\EnclosedDocs\Dokument”.
22. Kliknij opcję Powiąż.
23. Kliknij przycisk Zapisz.
24. Zamknij stronę.

