---
title: Konfigurowanie BOPIS w środowisku oceny usługi Dynamics 365 Commerce
description: W tym temacie opisano sposób konfigurowania modułu kupowanie online, odbiór w sklepie (BOPIS) w środowisku ewaluacji Microsoft Dynamics 365 Commerce po jego zainicjowaniu.
author: BrianShook
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1e0aabec196aa1ffd2e4d2f2691c03cf11326ee8
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2021
ms.locfileid: "7779801"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-evaluation-environment"></a>Konfigurowanie BOPIS w środowisku oceny rozwiązania Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania modułu kupowanie online, odbiór w sklepie (BOPIS) w środowisku Microsoft Dynamics 365 Commerce po zainicjowaniu środowiska.

## <a name="prerequisite"></a>Wymaganie wstępne

Procedury opisane w tym temacie należy wykonać dopiero po zakończeniu aprowizacji i konfiguracji środowiska oceny wersji zapoznawczej usługi Commerce. Aby uzyskać informacje dotyczące sposobu prowizji i konfigurowania środowiska, zobacz [Inicjowaniw środowiska oceny wersji zapoznawczej Dynamics 365 Commerce](provisioning-guide.md) i [Konfiguracja środowiska oceny wersji zapoznawczej Dynamics 365 Commerce](./cpe-post-provisioning.md).

Po zainicjowaniu obsługi i skonfigurowaniu środowiska Commerce można skorzystać z tego tematu w celu włączenia scenariuszy BOPIS.

## <a name="configure-the-pos"></a>Konfigurowanie punktu sprzedaży POS

### <a name="configure-modern-pos"></a>Konfiguracja Modern POS

Scenariusze BOPIS, które obejmują płatność kartą kredytową, wymagają stacji sprzętowej. Stacja sprzętowa jest wbudowana w Modern POS dla systemu Windows i klientach Android. Jeśli w systemie iOS jest używany program Cloud POS lub Modern POS, klient punktu sprzedaży (POS) musi być sparowany z udostępnioną stacją sprzętową. W tym temacie wyjaśniono, jak skonfigurować BOPIS dla systemu Windows i klientów Android. Aby uzyskać więcej informacji dotyczących sposobu konfiguracji współużytkowanej stacji sprzętowej, zobacz [Konfiguracja i instalacja programu Retail hardware station](./retail-hardware-station-configuration-installation.md).

1. Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Rejestry**.
2. Wybierz rejestr **SANFRAN-5**, a następnie wybierz opcję **Edytuj**.
3. Zmień wartość pola **Profil sprzętu** z **HW002** na **HW001**, a następnie wybierz opcję **Zapisz**.
4. Aby zsynchronizować zmiany, przejdź do **Retail i Commerce \> Retail i Commerce — składniki IT \> Harmonogram dystrybucji**.
5. Wybierz harmonogram dystrybucji **1090**, a następnie w okienku akcji wybierz opcję **Uruchom teraz**.
6. Wybierz **Tak**, a następnie kliknij przycisk **OK**, aby zainicjować synchronizację danych. 

### <a name="install-modern-pos"></a>Zainstaluj Modern POS

1. Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Urządzenia**.
2. Wybierz urządzenie **SANFRANCIS-5**.
3. W okienku akcji wybierz opcję **Pobierz**, a następnie wybierz opcję **Konfiguracja pliku**.
4. Wybierz kolejno opcje **Pobierz** i **Retail Modern POS**. 
5. Po zakończeniu pobierania pliku **ModernPOSSetup.exe** wybierz opcję **Otwórz plik**.

    ![Otwórz plik.](./dev-itpro/media/PAYMENTS/openfile.png)

6. Wybierz przycisk **Dalej**, aby przejść przez proces instalacji. Po zakończeniu instalacji wybierz opcję **Zamknij**.

### <a name="activate-modern-pos"></a>Aktywuj Modern POS

1. Na pulpicie systemu Windows wybierz przycisk **Start** i wprowadź **Retail Modern POS**.
2. Wybierz aplikację **Retail Modern POS**, aby zainicjować aktywację.
3. Wybierz pozycję **Następny**. Pola **Adres URL serwera**, **Identyfikator urządzenia** i **Numer rejestru** powinny być wstępnie ustawione przy użyciu informacji z pliku konfiguracji pobranego w poprzedniej procedurze.
4. Wybierz **Aktywuj**.
5. Pojawi się okno dialogowe uwierzytelniania. Wybierz konto korzystające z adresu e-mail, który był poprzednio skojarzony z pracownikiem **000713 - Andrew Collette**.

    > [!NOTE]
    > Jeśli użytkownik nie jest jeszcze skojarzony z tożsamością pracownika, aktywacja nie powiedzie się. W takim przypadku należy wykonać kroki opisane w sekcji „Kojarzenie pracownika z Twoją tożsamością” w temacie [Konfigurowanie środowiska oceny wersji zapoznawczej usługi Dynamics 365 Commerce](cpe-post-provisioning.md#associate-a-worker-with-your-identity).
    
6. Gdy zostanie wyświetlony monit o zarządzanie urządzeniem, wybierz **Tylko ta aplikacja**.
7. Po zakończeniu aktywacji wybierz opcję **Rozpoczynanie pracy**.

### <a name="enable-bopis-in-modern-pos"></a>Włącz BOPIS w Modern POS

1. Zaloguj się do Modern POS, używając **000713** jako identyfikatora operatora i **123** jako hasła.
2. Podczas odtwarzania wideo z instruktażem wprowadzającym należy zaznaczyć dwa pola wyboru w lewym dolnym rogu okna dialogowego, a następnie zamknąć okno dialogowe.
3. Jeśli nie zostanie wyświetlony monit o zamknięcie zmiany, przewiń tekst do prawej strony **powitalnej**, wybierz opcję **Zamknij zmianę**, a następnie zaloguj się ponownie do punktu sprzedaży.
4. Po zalogowaniu się, gdy zostanie wyświetlony monit, wybierz opcję **Wykonaj operację bez użycia szuflady**.
5. Na stronie **powitalnej** przewiń w prawo i wybierz operację **Wybierz stację sprzętową** .
6. Wybierz **Zarządzaj**, ustaw opcję **Użyj stacji sprzętowej** na **Włączona**, a następnie kliknij **OK**.
7. Wyloguj się z kasy POS, a następnie ponownie zaloguj.
8. Po zalogowaniu się wybierz opcję **Otwórz nową zmianę**, a następnie wybierz **Szuflada**.

## <a name="complete-a-bopis-scenario"></a>Ukończ scenariusz BOPIS

### <a name="create-a-storefront-order-for-in-store-pickup"></a>Tworzenie zamówienia sklepu na potrzeby odbioru w sklepie

1. Umożliwia przejście do adresu URL, który został określony w kroku [Inicjalizowanie e-Commerce](./provisioning-guide.md#initialize-e-commerce) podczas konfigurowania środowiska.
2. Wybierz towar i wybierz opcję **Dodaj do koszyka**.
3. Na stronie koszyka, wybierz **Odbierz tę pozycję** dla dodanego właśnie wiersza zamówienia.
4. W oknie dialogowym **Wybierz sklep** wprowadź wartość **San Francisco**, a następnie wybierz przycisk **Wyszukaj**.
5. Na liście wyników znajdź sklep Francisco ii wybierz pozycję **Odbierz tu**.
6. Na stronie koszyka wybierz opcję **Realizacja zamówienia jako gość**. 

    > [!NOTE]
    > Aby kontynuować proces realizacji transakcji, musisz zaakceptować powiadomienie o plikach cookie. Ta informacja jest wyświetlana jako transparent u góry strony realizacja transakcji.

7. W przypadku metody płatności kartą kredytową wprowadź następujące informacje:

    - **Nazwa posiadacza karty**: Wprowadź dowolną nazwę.
    - **Numer karty:** Wprowadź **4111-1111-1111-1111**.
    - **Data ważności:** Wprowadź **10/20**.
    - **Kod weryfikacji karty (CVV):** Wprowadź **737**.

    > [!IMPORTANT]
    > Nigdy w żadnym wypadku nie próbuj używać rzeczywistych informacji o karcie kredytowej w witrynie testowej.

8. Kontynuuj proces realizacji transakcji, wprowadzając szczegóły adresu fakturowania, a następnie wybierz opcję **Zapisz i kontynuuj**.
9. Gdy zamówienie jest gotowe do umieszczenia, wybierz opcję **Realizacja zamówienia**.

### <a name="synchronize-online-orders-to-the-back-office"></a>Synchronizuj zamówienia online w biurze zaplecza

Aby uzyskać informacje na temat synchronizowania zamówień online, zapoznaj się z tematem [Księgowanie sprzedaży i płatności online](./tasks/posting-online-sales-payments.md).

### <a name="pick-up-an-order-in-the-store"></a>Odbiór zamówienia w sklepie

1. Zaloguj się w kasie POS.
2. Na ekranie **powitalnym** wybierz opcję **Realizacja zamówienia**
3. Na liście towarów do odbioru zaznacz wiersz w zamówieniu, który został umieszczony w trybie online.
4. Po wybraniu wiersza zamówienia wybierz opcję **Odbierz**.

    Wiersz towaru jest dodawany do ekranu transakcji, a **$0,00** jest wyświetlane jako saldo należne.

5. Wybierz saldo należne w wysokości **$0,00** lub wybierz dowolną metodę płatności, aby zawrzeć transakcję.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a>Zamówienia online odbierane w punkcie sprzedaży mają niezerowe saldo należne

Jeśli zamówienie jest pobierane na potrzeby odbioru w sklepie, jeśli saldo należne nie jest równe 0 (zero), należy się upewnić, że jest używany Modern POS, a stacja sprzętowa jest aktywna. Jeśli jest używane Cloud POS lub Modern POS dla systemu iOS, upewnij się, że udostępniona stacja sprzętowa jest aktywna. Niektóre formy aktywnej stacji sprzętowej są wymagane do pobierania płatności, które zostały wprowadzone w trybie online.

### <a name="general-issues-with-payment-capture"></a>Ogólne problemy z przechwyceniem płatności

Aby uzyskać wszystkie ogólne problemy, należy zawsze najpierw zapoznać się z dziennikami zdarzeń Modern POS lub Internet Information Services (IIS). Te dzienniki można znaleźć w następujących węzłach w dzienniku zdarzeń systemu Windows:

- Dzienniki aplikacji i usług \> Microsoft \> Dynamics \> Commerce-ModernPOS
- Dzienniki aplikacji i usług \> Microsoft \> Dynamics \> Commerce-Hardware Station

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie środowiska oceny usługi Dynamics 365 Commerce](cpe-overview.md)

[Ustanowienie środowiska oceny Dynamics 365 Commerce](provisioning-guide.md)

[Konfigurowanie opcjonalnych funkcji środowiska oceny Dynamics 365 Commerce](cpe-optional-features.md)

[Środowiska oceny usługi Dynamics 365 Commerce — często zadawane pytania](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Witryna Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Łącznik płatności Adyen](./dev-itpro/adyen-connector.md?tabs=8-1-3)

[Zapisywanie instrumentów płatniczych online za pomocą łącznika Adyen](./dev-itpro/adyen-connector-listpi.md)

[Omówienie płatności wielokanałowych](./omni-channel-payments.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]