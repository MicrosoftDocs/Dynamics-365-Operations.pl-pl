--- 
title: "Rozszerzanie modelu danych w celu używania plików zarządzania dokumentami w danych wyjściowych formatu na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników)."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f3d494cc83b273eef071b23d0948b283ba85c17e
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="extend-data-model-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a>Rozszerzanie modelu danych w celu używania plików zarządzania dokumentami w danych wyjściowych formatu na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników). Kroki można wykonać na danych dowolnej firmy.

W celu wykonania tych kroków należy najpierw wykonać kroki opisane w przewodniku po zadaniu „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 1: Przygotowanie modelu danych)”.

Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a>Rozszerzanie modelu danych w celu przedstawienia w nim plików zarządzania dokumentami
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Konfiguracje raportowania.
3. W drzewie rozwiń węzeł „Model faktur sprzedaży”.
4. W drzewie zaznacz element „Model faktur sprzedaży\Model faktur sprzedaży (niestandardowy)”.
5. Kliknij przycisk Konstruktor.
6. W drzewie zaznacz element „Faktura dla odbiorcy(InvoiceCustomer)”.
    * Rozszerzymy ten model danych w celu udostępnienia w nim wszystkich plików, które zostały dołączone do zamówienia sprzedaży powiązanego z elektronicznie przetworzoną fakturą.  
7. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
8. W polu Nazwa wpisz „Załączniki faktur”.
    * Załączniki faktur  
9. W polu Typ elementu wybierz opcję „Lista rekordów”.
10. Kliknij przycisk Dodaj.
11. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
12. W polu Nazwa wpisz „Zawartość pliku”.
    * Zawartość pliku  
13. W polu Typ elementu wybierz opcję „Kontener”.
14. Kliknij przycisk Dodaj.
15. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
16. W polu Nazwa wpisz „Nazwa pliku”.
    * Nazwa pliku  
17. W polu Typ elementu wybierz opcję „Ciąg”.
18. Kliknij przycisk Dodaj.

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-enterprise-edition-data-sources"></a>Mapowanie elementów nowego modelu danych na źródła danych programu Dynamics 365 for Finance and Operations Enterprise Edition
1. Kliknij opcję Mapuj model na źródło danych.
2. Użyj szybkiego filtru, aby wyfiltrować pole Definicja według wartości „InvoiceCustomer”.
    * InvoiceCustomer  
    * Zmapujemy elementy nowego modelu na odpowiednie źródła danych.  
3. Kliknij przycisk Konstruktor.
4. W drzewie zaznacz element „Załączniki faktur”.
5. W drzewie rozwiń węzeł „Załączniki faktur”.
6. W drzewie zaznacz element „Załączniki faktur\Nazwa pliku”.
7. Kliknij przycisk Edytuj.
8. W polu Formuła wpisz wyrażenie „CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'originalFileName()'”.
    * CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'originalFileName()'  
9. Kliknij przycisk Zapisz.
10. Zamknij stronę.
11. W drzewie zaznacz element „Załączniki faktur\Zawartość pliku”.
12. Kliknij przycisk Edytuj.
13. W polu Formuła wpisz wyrażenie „CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'getFileContentAsContainer()'”.
    * CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'.'getFileContentAsContainer()'  
14. Kliknij przycisk Zapisz.
15. Zamknij stronę.
16. W drzewie zaznacz element „Załączniki faktur”.
17. Kliknij przycisk Edytuj.
18. W polu Formuła wpisz wyrażenie „CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'”.
    * CustInvoiceJour.'>Relacje'.SalesTable.'<Relacje'.'<Dokumenty'  
19. Kliknij przycisk Zapisz.
20. Zamknij stronę.
21. Kliknij przycisk Zapisz.
22. Zamknij stronę.
23. Zamknij stronę.
24. Zamknij stronę.
25. Kliknij przycisk Zmień stan.
26. Kliknij przycisk Wykonaj.
27. Kliknij przycisk OK.

