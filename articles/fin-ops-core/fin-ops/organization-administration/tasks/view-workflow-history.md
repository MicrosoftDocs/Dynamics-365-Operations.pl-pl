---
title: Wyświetlanie historii przepływu pracy
description: W tym temacie opisano wyświetlenie stanu dokumentu przesłanego do systemu przepływu pracy w celu przetworzenia i zatwierdzenia.
author: jasongre
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3d7118e85ff56f8c935c24a91dc84c6cc09641e0
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694318"
---
# <a name="view-workflow-history"></a>Wyświetlanie historii przepływu pracy

[!include [banner](../../includes/banner.md)]

W tym temacie opisano wyświetlenie stanu dokumentu przesłanego do systemu przepływu pracy w celu przetworzenia i zatwierdzenia. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

1. Otwórz **Okienko nawigacji > Moduły > Wspólne > Informacje > Przepływu pracy > Historia przepływu pracy**.
    - Ten formularz umożliwia wyświetlenie stanu dokumentu przesłanego do przepływu pracy w celu przetworzenia i zatwierdzenia.  
    - Opcja **Identyfikator wystąpienia** to kod identyfikacyjny wystąpienia przepływu pracy, w ramach którego jest przetwarzany lub został przetworzony dokument.  
    - Opcja **Stan** to stan dokumentu w przepływie pracy.  
    - Opcja **Identyfikator przepływu pracy** to kod identyfikacyjny przepływu pracy, w ramach którego jest przetwarzany lub został przetworzony dokument.  
    - Opcja **Dokument** to kod identyfikacyjny dokumentu.  
    - Opcja **Typ dokumentu** to typ dokumentu przesłanego do przetwarzania.  
    - Opcja **Przepływ pracy** to nazwa przepływu pracy, w ramach którego jest przetwarzany lub został przetworzony dokument.  
    - Opcja **Wersja** to numer wersji przepływu pracy, w ramach którego jest przetwarzany lub został przetworzony dokument.  
    - Opcja **Data i godzina utworzenia** to data i godzina przesłania dokumentu.  
    - Opcja **Upłynęło czasu** to ilość czasu, jaka upłynęła od przesłania dokumentu.  
    - Przycisk **Wznów** umożliwia wznowienie procesu przepływu pracy dla wybranego dokumentu.  
    - Przycisk **Wycofaj** umożliwia wycofywanie wybranego dokumentu, tak aby nie był przetwarzany.   
2. Na liście wybierz łącze w odpowiednim wierszu.
    - Upewnij się, że jest rozwinięta sekcja **Elementy pracy**. W tej sekcji można obejrzeć elementy pracy skojarzone z wybranym dokumentem. Na przykład może być konieczne wykonanie zadania lub zatwierdzenie dokumentu.  
    - Przycisk **Przypisz** ponownie powoduje otwarcie okna dialogowego, w którym można przepisać element pracy do innego użytkownika.  
    - Upewnij się, że jest rozwinięta sekcja **Szczegóły śledzenia**. W tej sekcji można obejrzeć historię przepływu pracy dla wybranego dokumentu.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]