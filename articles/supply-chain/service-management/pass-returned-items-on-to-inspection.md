---
title: Przekazywanie zwróconych towarów do inspekcji
description: Rejestrując zwrócony towar, można określić, że przed zwróceniem do magazynu lub likwidacją towar powinien zostać wysłany do inspekcji.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70aafb752b2c847d5d48236fd5d201a73e088c24
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "334089"
---
# <a name="pass-returned-items-on-to-inspection"></a>Przekazywanie zwróconych towarów do inspekcji 

[!include [banner](../includes/banner.md)]


Rejestrując zwrócony towar, można określić, że przed zwróceniem do magazynu lub likwidacją towar powinien zostać wysłany do inspekcji.

1.  Wybierz kolejno opcje **Zarządzanie zapasami** \> **Arkusze** \> **Przyjęcie pozycji** \> **Przyjęcie pozycji**.
    
    \-lub-
    
    Wybierz kolejno opcje **Zarządzanie zapasami** \> **Arkusze** \> **Przyjęcie pozycji** \> **Przyjęcie z produkcji**.

2.  W formularzu **Arkusz lokalizacji** zarejestruj przyjęcie towaru w zwykły sposób.
    

    > [!NOTE]
    > <P>Aby uzyskać informacje o rejestrowaniu przyjęcia zwróconych towarów, zobacz <A href="register-the-receipt-of-returned-items.md">Rejestrowanie przyjęcia zwróconych towarów</A></P>



3.  Na karcie **Wartości domyślne** w obszarze **Tryb obsługi** zaznacz pole wyboru **Zarządzanie kwarantanną**.

Spowoduje to utworzenie w systemie zlecenia kwarantanny, a osoba lub dział wykonujący inspekcje odpowie na to zlecenie za pomocą formularza **Zlecenie kwarantanny**.

## <a name="see-also"></a>Informacje dodatkowe

[Poddawanie zwróconych towarów inspekcji](take-returned-items-through-inspection.md)

[Określanie sposobu likwidacji zwróconych towarów](specify-how-to-dispose-of-returned-items.md)

