---
title: Tworzenie i kojarzenie stacji sprzętowej
description: Ta procedura zawiera instruktaż tworzenia nowej stacji sprzętowej.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailHardwareStation, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 305308b0e4ba99aae4bf6f8f94041db570a25893
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414997"
---
# <a name="create-and-associate-a-hardware-station"></a>Tworzenie i kojarzenie stacji sprzętowej

[!include [banner](../includes/banner.md)]

Ta procedura zawiera instruktaż tworzenia nowej stacji sprzętowej. Nowy profil sprzętu zostanie utworzony i użyty w celu dodania nowych stacji sprzętowych do wstępnie zdefiniowanego sklepu (kanału). Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz kolejno opcje Podstawowe funkcje handlowe > Kanały > .. > .. > .. > Profile stacji sprzętowych.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator stacji sprzętowej wpisz „TestHWProfile”.
4. W polu Nazwa wpisz wartość.
5. W polu Numer portu wprowadź liczbę.
6. W polu Profil sprzętu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. Na liście kliknij łącze w wybranym wierszu.
9. W polu Nazwa pakietu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
10. Na liście kliknij łącze w wybranym wierszu.
    * Jest to standardowy pakiet towarzyszący nowemu środowisku. Numer wersji może się różnić.  
11. Kliknij przycisk Zapisz.
12. Zamknij stronę.
13. Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Wszystkie sklepy.
14. Na liście zaznacz wiersz 17.
    * Jeśli używasz danych firmy demonstracyjnej USRT, jest to sklep w Houston.  
15. Na liście kliknij łącze w wybranym wierszu.
16. Przełącz rozwinięcie sekcji Stacje sprzętowe.
17. Kliknij przycisk Dodaj.
18. Na liście oznacz wybrany wiersz.
19. W polu Identyfikator profilu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
20. Na liście znajdź i zaznacz odpowiedni rekord.
    * Musi to być nowy profil stacji sprzętowej, który został utworzony w poprzednich krokach.  
21. Na liście kliknij łącze w wybranym wierszu.
22. W polu Nazwa hosta wpisz wartość.
23. W polu Identyfikator terminalu EFT wpisz wartość.
24. Kliknij przycisk Zapisz.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]