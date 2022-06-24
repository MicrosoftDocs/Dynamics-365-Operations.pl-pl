---
title: ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 2 — Rozszerzanie modelu danych)
description: W tym artykule opisano sposób konfigurowania formatu raportowania elektronicznego (ER) do używania plików zarządzania dokumentami (załączników) w danych wyjściowych ER. (część 2)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2488aeaae4d856444ea14e26e2232405ec27a25f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908363"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a>ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 2 — Rozszerzanie modelu danych)

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników). Kroki można wykonać na danych dowolnej firmy.

W celu wykonania tych kroków należy najpierw wykonać kroki opisane w przewodniku po zadaniu „ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 1: Przygotowanie modelu danych)”.

Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.


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

## <a name="map-new-data-model-elements-to-data-sources"></a>Mapowanie elementów nowego modelu danych na źródła danych
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



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]