---
title: Tworzenie profilu funkcji handlu detalicznego
description: W tym artykule opisano sposób tworzenia profilu funkcji w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: f006aaf594f1df097f80c77794e34f9b831e9949
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280249"
---
# <a name="create-a-retail-functionality-profile"></a>Tworzenie profilu funkcji handlu detalicznego

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób tworzenia profilu funkcji w rozwiązaniu Microsoft Dynamics 365 Commerce.

Profil funkcji handlu umożliwia używanie różnych ustawień dla kanałów online. Każdy kanał musi określać profil funkcji.

## <a name="create-a-functionality-profile"></a>Tworzenie profilu funkcji

Aby utworzyć profil funkcji, wykonaj poniższe kroki.

1. W okienku nawigacji przejdź do ustawień **Moduły \> Ustawienia kanału \> Profile punktu sprzedaży \> Profile funkcji**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **profil** wprowadź identyfikator profilu („FN006” w poniższym obrazie poniżej).
1. W polu **opis** wprowadź wartość („profil Adventure Works” w poniższym obrazie poniżej).
1. W sekcji **ogólne** wybierz kraj dla ustawień regionalnych **ISO**.
1. W sekcji **ogólne** zmodyfikuj inne ustawienia, jeśli jest to konieczne.
1. W sekcji **ogólne** wybierz **identyfikator profilu paragonów** dla paragonów w wiadomościach e-mail.
1. W sekcji **Funkcje** zmodyfikuj inne ustawienia, jeśli jest to konieczne.
1. W sekcji **Ilość** zmodyfikuj inne ustawienia, jeśli jest to konieczne.
1. W sekcji **Kody informacji** zmodyfikuj inne ustawienia, jeśli jest to konieczne.
1. W sekcji **Numeracja paragonów** zmodyfikuj inne ustawienia, jeśli jest to konieczne. 
  
Poniższy obraz przedstawia przykładowy profil funkcji.
  
![Przekład profilu funkcji.](media/retail-functionality-profile.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Kody informacji i grupy kodów informacji](info-codes-retail.md)           

[Tworzenie nowej książki adresowej](new-address-book.md) 

[Omówienie układu ekranu](pos-screen-layouts.md)       

[Konfigurowanie i instalowanie modułu Retail Hardware Station](retail-hardware-station-configuration-installation.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
