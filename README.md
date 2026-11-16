# Booking XML RAW Booking Phức Tạp Hoàn Chỉnh (OTA_ResRetrieveRS)
Dưới đây là bản tin XML RAW chuẩn theo định dạng SOAP Envelope của Exely PMSConnect, chứa đầy đủ các tình huống nghiệp vụ phức tạp nhất:

```
<s:Envelope>
  <s:Body>
    <OTA_ResRetrieveRS Version="1.18">
      <Success/>
      <ReservationsList>
        <HotelReservation CreateDateTime="2026-11-16T17:01:52.423" LastModifyDateTime="2026-11-16T17:01:56.357" ResStatus="Confirmed">
          
          <!-- 1. THÔNG TIN ĐIỂM BÁN HÀNG & KÊNH ĐẶT PHÒNG (POS & BOOKING CHANNEL) -->
          <POS>
            <Source>
              <RequestorID Type="22" ID="PMSConnect"/>
              <BookingChannel Type="7">
                <CompanyName Code="BGC" CodeContext="PMSConnect">OTA Distribution Channel</CompanyName>
              </BookingChannel>
            </Source>
          </POS>

          <!-- 2. MÃ ĐỊNH DANH ĐƠN ĐẶT PHÒNG (BOOKING UNIQUE IDs) -->
          <UniqueID Type="14" ID="20261216-501661-1200423651"/>
          <UniqueID Type="9" ID="GRP-9988421" ID_Context="External"/>

          <!-- 3. DANH SÁCH CÁC PHÒNG ĐẶT (ROOM STAYS) -->
          <RoomStays>
            
            <!-- PHÒNG 1 (IndexNumber="2029032"): Executive Family Suite - 3 Người lớn (2 giường chính + 1 giường phụ) & 2 Trẻ em -->
            <RoomStay IndexNumber="2029032">
              <RoomTypes>
                <RoomType RoomTypeCode="5001574" InvBlockCode="5000456" Quantity="1"/>
              </RoomTypes>
              <RatePlans>
                <RatePlan RatePlanID="10011297"/>
              </RatePlans>
              
              <!-- Giá phòng chi tiết theo từng ngày (Daily Rates & Taxes) -->
              <RoomRates>
                <!-- Đêm 1: 16/12/2026 -->
                <RoomRate EffectiveDate="2026-12-16" ExpireDate="2026-12-16" RatePlanCode="10011297">
                  <Total AmountBeforeTax="2500000.00" AmountAfterTax="2750000.00" CurrencyCode="VND">
                    <Taxes Amount="250000.00">
                      <Tax Code="VAT" Amount="250000.00" Percent="10.00">
                        <TaxDescription><Text>Thuế giá trị gia tăng VAT 10%</Text></TaxDescription>
                      </Tax>
                    </Taxes>
                  </Total>
                  <!-- Phân rã tiền phòng chi tiết cho từng khách lưu trú (PlacementRates) -->
                  <TPA_Extensions>
                    <PlacementRates>
                      <PlacementRate ResGuestRPH="1" RatePlanCode="10011297">
                        <Total AmountAfterTax="1000000.00" CurrencyCode="VND"/>
                      </PlacementRate>
                      <PlacementRate ResGuestRPH="2" RatePlanCode="10011297">
                        <Total AmountAfterTax="1000000.00" CurrencyCode="VND"/>
                      </PlacementRate>
                      <PlacementRate ResGuestRPH="3" RatePlanCode="10011297">
                        <Total AmountAfterTax="500000.00" CurrencyCode="VND"/>
                      </PlacementRate>
                      <PlacementRate ResGuestRPH="4" RatePlanCode="10011297">
                        <Total AmountAfterTax="250000.00" CurrencyCode="VND"/>
                      </PlacementRate>
                    </PlacementRates>
                  </TPA_Extensions>
                </RoomRate>
                
                <!-- Đêm 2: 17/12/2026 -->
                <RoomRate EffectiveDate="2026-12-17" ExpireDate="2026-12-17" RatePlanCode="10011297">
                  <Total AmountBeforeTax="2500000.00" AmountAfterTax="2750000.00" CurrencyCode="VND">
                    <Taxes Amount="250000.00">
                      <Tax Code="VAT" Amount="250000.00" Percent="10.00">
                        <TaxDescription><Text>Thuế giá trị gia tăng VAT 10%</Text></TaxDescription>
                      </Tax>
                    </Taxes>
                  </Total>
                  <TPA_Extensions>
                    <PlacementRates>
                      <PlacementRate ResGuestRPH="1" RatePlanCode="10011297">
                        <Total AmountAfterTax="1000000.00" CurrencyCode="VND"/>
                      </PlacementRate>
                      <PlacementRate ResGuestRPH="2" RatePlanCode="10011297">
                        <Total AmountAfterTax="1000000.00" CurrencyCode="VND"/>
                      </PlacementRate>
                      <PlacementRate ResGuestRPH="3" RatePlanCode="10011297">
                        <Total AmountAfterTax="500000.00" CurrencyCode="VND"/>
                      </PlacementRate>
                      <PlacementRate ResGuestRPH="4" RatePlanCode="10011297">
                        <Total AmountAfterTax="250000.00" CurrencyCode="VND"/>
                      </PlacementRate>
                    </PlacementRates>
                  </TPA_Extensions>
                </RoomRate>
              </RoomRates>

              <!-- Phân rã số lượng khách & loại giường (GuestCounts) -->
              <GuestCounts>
                <GuestCount AgeQualifyingCode="AdultBed" Count="1" ResGuestRPH="1"/>
                <GuestCount AgeQualifyingCode="AdultBed" Count="1" ResGuestRPH="2"/>
                <GuestCount AgeQualifyingCode="AdultExtraBed" Count="1" ResGuestRPH="3"/>
                <GuestCount AgeQualifyingCode="ChildBandBed" Count="1" Age="8" ResGuestRPH="4"/>
                <GuestCount AgeQualifyingCode="ChildBandWithoutBed" Count="1" Age="3" ResGuestRPH="5"/>
              </GuestCounts>

              <!-- Thời gian lưu trú của Phòng 1 -->
              <TimeSpan Start="2026-12-16T14:00:00" Duration="2" End="2026-12-18T12:00:00"/>

              <!-- Thông tin chiết khấu áp dụng cho phòng (Discounts) -->
              <Discounts>
                <Discount DiscountCode="PROMO10" AmountAfterTax="550000.00" Percent="10.00" Type="Percent">
                  <DiscountReason><Text>Giảm giá khuyến mãi mùa đông Early Bird 10%</Text></DiscountReason>
                </Discount>
              </Discounts>

              <!-- Điều khoản phạt hủy phòng (CancelPenalties) -->
              <CancelPenalties CancelPolicyIndicator="true">
                <CancelPenalty>
                  <Deadline AbsoluteDeadline="2026-12-15T07:00:00Z"/>
                  <AmountPercent NmbrOfNights="1" BasisType="Nights" CurrencyCode="VND" Amount="2750000"/>
                  <PenaltyDescription>
                    <Text>Hủy phòng trước 24h so với 14:00 ngày nhận phòng miễn phí. Hủy dưới 24h tính phí 1 đêm đầu tiên.</Text>
                  </PenaltyDescription>
                </CancelPenalty>
              </CancelPenalties>

              <!-- Tổng tiền của Phòng 1 -->
              <Total AmountBeforeTax="5000000.00" AmountAfterTax="5500000.00" CurrencyCode="VND" DecimalPlaces="0"/>
              <BasicPropertyInfo HotelCode="501661"/>
              
              <!-- Liên kết với các dịch vụ phụ trợ trong tag Services -->
              <ServiceRPHs>
                <ServiceRPH RPH="1"/>
                <ServiceRPH RPH="2"/>
              </ServiceRPHs>
            </RoomStay>

            <!-- PHÒNG 2 (IndexNumber="2029033"): Deluxe Double - RateMix (2 đêm 2 gói giá khác nhau) & 1 Người lớn + 1 Em bé -->
            <RoomStay IndexNumber="2029033">
              <RoomTypes>
                <RoomType RoomTypeCode="5001580" InvBlockCode="5000456" Quantity="1"/>
              </RoomTypes>
              <RatePlans>
                <RatePlan RatePlanID="10011297"/>
                <RatePlan RatePlanID="10011298"/>
              </RatePlans>
              <RoomRates>
                <!-- Đêm 1: Gói giá 10011297 -->
                <RoomRate EffectiveDate="2026-12-16" ExpireDate="2026-12-16" RatePlanCode="10011297">
                  <Total AmountBeforeTax="1500000.00" AmountAfterTax="1650000.00" CurrencyCode="VND"/>
                </RoomRate>
                <!-- Đêm 2: Gói giá 10011298 (RateMix) -->
                <RoomRate EffectiveDate="2026-12-17" ExpireDate="2026-12-17" RatePlanCode="10011298">
                  <Total AmountBeforeTax="1800000.00" AmountAfterTax="1980000.00" CurrencyCode="VND"/>
                </RoomRate>
              </RoomRates>
              <GuestCounts>
                <GuestCount AgeQualifyingCode="AdultBed" Count="1" ResGuestRPH="6"/>
                <GuestCount AgeQualifyingCode="ChildBandWithoutBed" Count="1" Age="1" ResGuestRPH="7"/>
              </GuestCounts>
              <TimeSpan Start="2026-12-16T14:00:00" Duration="2" End="2026-12-18T12:00:00"/>
              <Total AmountBeforeTax="3300000.00" AmountAfterTax="3630000.00" CurrencyCode="VND"/>
              <BasicPropertyInfo HotelCode="501661"/>
              <ServiceRPHs>
                <ServiceRPH RPH="3"/>
                <ServiceRPH RPH="4"/>
              </ServiceRPHs>
            </RoomStay>
          </RoomStays>

          <!-- 4. DANH SÁCH KHÁCH LƯU TRÚ THỰC TẾ (RES GUESTS) -->
          <ResGuests>
            <!-- Khách 1: Người lớn 1 (Phòng 1) - Trưởng đoàn/Khách chính -->
            <ResGuest ResGuestRPH="1">
              <Profiles>
                <ProfileInfo>
                  <UniqueID Type="21" ID="1200475652" ID_Context="PMSConnect"/>
                  <Profile>
                    <Customer Gender="Male" BirthDate="1985-05-20">
                      <PersonName>
                        <GivenName>John</GivenName>
                        <MiddleName>A.</MiddleName>
                        <Surname>Smith</Surname>
                      </PersonName>
                      <CitizenCountryName Code="GBR"/>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>
            
            <!-- Khách 2: Người lớn 2 (Phòng 1) -->
            <ResGuest ResGuestRPH="2">
              <Profiles>
                <ProfileInfo>
                  <UniqueID Type="21" ID="1200475653" ID_Context="PMSConnect"/>
                  <Profile>
                    <Customer Gender="Female" BirthDate="1988-08-15">
                      <PersonName>
                        <GivenName>Mary</GivenName>
                        <MiddleName>B.</MiddleName>
                        <Surname>Smith</Surname>
                      </PersonName>
                      <CitizenCountryName Code="GBR"/>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>

            <!-- Khách 3: Người lớn 3 ở Giường Phụ (Phòng 1) -->
            <ResGuest ResGuestRPH="3">
              <Profiles>
                <ProfileInfo>
                  <UniqueID Type="21" ID="1200475654" ID_Context="PMSConnect"/>
                  <Profile>
                    <Customer Gender="Male" BirthDate="1990-12-01">
                      <PersonName>
                        <GivenName>David</GivenName>
                        <Surname>Smith</Surname>
                      </PersonName>
                      <CitizenCountryName Code="GBR"/>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>

            <!-- Khách 4: Trẻ em có giường phụ (Phòng 1) -->
            <ResGuest ResGuestRPH="4">
              <Profiles>
                <ProfileInfo>
                  <UniqueID Type="21" ID="1200475655" ID_Context="PMSConnect"/>
                  <Profile>
                    <Customer Gender="Male" BirthDate="2018-03-10">
                      <PersonName>
                        <GivenName>Tommy</GivenName>
                        <Surname>Smith</Surname>
                      </PersonName>
                      <CitizenCountryName Code="GBR"/>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>

            <!-- Khách 5: Trẻ em chung giường (Phòng 1) -->
            <ResGuest ResGuestRPH="5">
              <Profiles>
                <ProfileInfo>
                  <UniqueID Type="21" ID="1200475656" ID_Context="PMSConnect"/>
                  <Profile>
                    <Customer Gender="Female" BirthDate="2023-09-01">
                      <PersonName>
                        <GivenName>Alice</GivenName>
                        <Surname>Smith</Surname>
                      </PersonName>
                      <CitizenCountryName Code="GBR"/>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>

            <!-- Khách 6: Người lớn (Phòng 2) - Thành viên VIP Loyalty -->
            <ResGuest ResGuestRPH="6">
              <Profiles>
                <ProfileInfo>
                  <UniqueID Type="21" ID="1200475657" ID_Context="PMSConnect"/>
                  <Profile>
                    <Customer Gender="Female" BirthDate="1992-11-11">
                      <PersonName>
                        <GivenName>Emma</GivenName>
                        <Surname>Watson</Surname>
                      </PersonName>
                      <CitizenCountryName Code="USA"/>
                      <CustLoyalty ProgramID="EXELY_CLUB" MembershipID="VIP-998811" SignupDate="2022-01-01" LoyalLevel="GOLD" ExpireDate="2028-12-31">
                        <SubAccountBalance Balance="12500" Type="Points"/>
                      </CustLoyalty>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>

            <!-- Khách 7: Em bé (Phòng 2) -->
            <ResGuest ResGuestRPH="7">
              <Profiles>
                <ProfileInfo>
                  <UniqueID Type="21" ID="1200475658" ID_Context="PMSConnect"/>
                  <Profile>
                    <Customer Gender="Female" BirthDate="2025-06-01">
                      <PersonName>
                        <GivenName>Lily</GivenName>
                        <Surname>Watson</Surname>
                      </PersonName>
                      <CitizenCountryName Code="USA"/>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>
          </ResGuests>

          <!-- 5. THÔNG TIN TỔNG QUAN, NGƯỜI THANH TOÁN & ĐẶT CỌC (RES GLOBAL INFO) -->
          <ResGlobalInfo>
            <TimeSpan Start="2026-12-16T14:00:00" Duration="2" End="2026-12-18T12:00:00"/>
            
            <!-- Ghi chú đặc biệt từ khách hàng (Special Requests & Meal Plans) -->
            <Comments>
              <Comment Name="SpecialRequest">
                <Text>Khách muốn kê phòng tầng cao, giường phụ kê cạnh cửa sổ, hỗ trợ 01 nôi em bé cho Phòng 2.</Text>
              </Comment>
              <Comment Name="RoomTypeMealPlan">
                <Text>Bao gồm ăn sáng Buffet hàng ngày cho tất cả các khách lưu trú.</Text>
              </Comment>
            </Comments>

            <!-- Phương thức bảo đảm & Cổng thanh toán (Guarantee & Payment Gateways) -->
            <Guarantee GuaranteeCode="PrePay">
              <Comments>
                <Comment Name="PaymentMethodName"><Text>BankCard</Text></Comment>
                <Comment Name="PaymentSystemName"><Text>TLPAYMENTS</Text></Comment>
                <Comment Name="PaymentSystemTitle"><Text>Thanh toán trực tuyến qua thẻ ngân hàng Cổng Exely</Text></Comment>
                <Comment Name="PaymentSystemProfileAcquiringName"><Text>Hotel</Text></Comment>
                <Comment Name="PaymentTransactionId"><Text>TXN-20261216-99881234</Text></Comment>
              </Comments>
            </Guarantee>

            <!-- Chi tiết các khoản đặt cọc & thanh toán nhiều đợt (DepositPayments) -->
            <DepositPayments>
              <!-- Đợt 1: Đặt cọc lúc tạo đơn qua thẻ (ReceivedPayment - PaymentIndex 0) -->
              <GuaranteePayment Type="ReceivedPayment" PaymentIndex="0">
                <AmountPercent BasisType="Fixed" CurrencyCode="VND" Amount="3000000.00"/>
              </GuaranteePayment>
              
              <!-- Đợt 2: Thanh toán bổ sung trước chuyến đi (ReceivedPayment - PaymentIndex 1) -->
              <GuaranteePayment Type="ReceivedPayment" PaymentIndex="1">
                <AmountPercent BasisType="Fixed" CurrencyCode="VND" Amount="2000000.00"/>
              </GuaranteePayment>

              <!-- Đợt 3: Quy đổi điểm thưởng Loyalty (ReceivedLoyaltyPayment) -->
              <GuaranteePayment Type="ReceivedLoyaltyPayment">
                <AmountPercent BasisType="Fixed" CurrencyCode="VND" Amount="500000.00"/>
              </GuaranteePayment>
            </DepositPayments>

            <!-- Tổng chi phí toàn bộ đơn đặt phòng (bao gồm tiền phòng & thuế) -->
            <Total AmountBeforeTax="8300000.00" AmountAfterTax="10130000.00" CurrencyCode="VND">
              <Taxes Amount="830000.00">
                <Tax Code="VAT" Amount="830000.00" Percent="10.00">
                  <TaxDescription><Text>Thuế giá trị gia tăng VAT 10%</Text></TaxDescription>
                </Tax>
              </Taxes>
            </Total>

            <!-- Hồ sơ Người đứng tên thanh toán / Người đặt phòng (Payer / Customer) -->
            <Profiles>
              <ProfileInfo>
                <Profile>
                  <Customer Gender="Male" BirthDate="1985-05-20">
                    <PersonName>
                      <GivenName>John</GivenName>
                      <MiddleName>A.</MiddleName>
                      <Surname>Smith</Surname>
                    </PersonName>
                    <Telephone PhoneNumber="+447000000000"/>
                    <Email>guest.booking@example.com</Email>
                    <Address>
                      <AddressLine>Central Street 10</AddressLine>
                      <CityName>London</CityName>
                      <PostalCode>SW1A 2AA</PostalCode>
                      <StateProv StateCode="LDN"/>
                      <CountryName Code="GBR"/>
                    </Address>
                    <CitizenCountryName Code="GBR"/>
                  </Customer>
                </Profile>
              </ProfileInfo>
            </Profiles>
          </ResGlobalInfo>

          <!-- 6. DANH SÁCH DỊCH VỤ ĐI KÈM & PHỤ PHÍ (SERVICES & ADD-ONS) -->
          <Services>
            <!-- Dịch vụ 1: Ăn sáng Buffet (Bao gồm trong giá phòng - Inclusive="true", Amount = 0) -->
            <Service ServicePricingType="Per person per night" ServiceRPH="1" Inclusive="true" Quantity="5" ID="3742">
              <ServiceDetails>
                <TimeSpan Start="2026-12-16T00:00:00" Duration="2"/>
                <Comments>
                  <Comment Name="ServiceName"><Text>Breakfast Buffet</Text></Comment>
                </Comments>
                <Total AmountBeforeTax="0.00" AmountAfterTax="0.00" CurrencyCode="VND"/>
              </ServiceDetails>
            </Service>

            <!-- Dịch vụ 2: Đưa đón sân bay (Không bao gồm - Phụ phí 500,000 VND) -->
            <Service ServicePricingType="Per stay" ServiceRPH="2" Inclusive="false" Quantity="1" ID="3743" ServiceCategoryCode="Transfer">
              <ServiceDetails>
                <TimeSpan Start="2026-12-16T15:00:00" Duration="1"/>
                <Comments>
                  <Comment Name="TransferDetails">
                    <Text>Đón sân bay Nội Bài lúc 14:30, Chuyến bay VN212, Xe 7 chỗ Ford Transit</Text>
                  </Comment>
                </Comments>
                <Total AmountBeforeTax="454545.00" AmountAfterTax="500000.00" CurrencyCode="VND"/>
              </ServiceDetails>
            </Service>

            <!-- Dịch vụ 3: Phụ phí Nhận phòng sớm (Early Arrival - Phụ phí 300,000 VND) -->
            <Service ServicePricingType="Per use" ServiceRPH="3" Inclusive="false" Quantity="1" ID="3744" ServiceInventoryCode="EarlyArrival">
              <ServiceDetails>
                <TimeSpan Start="2026-12-16T08:00:00" Duration="1"/>
                <Comments>
                  <Comment Name="EarlyArrivalNotes"><Text>Nhận phòng sớm lúc 08:00 sáng ngày 16/12/2026</Text></Comment>
                </Comments>
                <Total AmountBeforeTax="272727.00" AmountAfterTax="300000.00" CurrencyCode="VND"/>
              </ServiceDetails>
            </Service>

            <!-- Dịch vụ 4: Phụ phí Trả phòng muộn (Late Departure - Phụ phí 200,000 VND) -->
            <Service ServicePricingType="Per use" ServiceRPH="4" Inclusive="false" Quantity="1" ID="3745" ServiceInventoryCode="LateDeparture">
              <ServiceDetails>
                <TimeSpan Start="2026-12-18T16:00:00" Duration="1"/>
                <Comments>
                  <Comment Name="LateDepartureNotes"><Text>Trả phòng muộn lúc 16:00 chiều ngày 18/12/2026</Text></Comment>
                </Comments>
                <Total AmountBeforeTax="181818.00" AmountAfterTax="200000.00" CurrencyCode="VND"/>
              </ServiceDetails>
            </Service>
          </Services>

        </HotelReservation>
      </ReservationsList>
    </OTA_ResRetrieveRS>
  </s:Body>
</s:Envelope>
```

# Checklist để kiểm tra hiển thị trên PMS:

# Exely Booking Integration – Comprehensive QA Checklist

> **Test Booking ID:** `20261216-501661-1200423651`  
> **Group ID:** `GRP-9988421`  
> **Booking Date:** 16/12/2026  
> **Total Rooms:** 2  
> **Total Guests:** 7

---

## MODULE 1. BOOKING HEADER & METADATA
*Thông tin chung đơn hàng*

- [ ] **1.1. Exely Channel ID** (`UniqueID Type="14"`)
  - Hiển thị đúng mã: `20261216-501661-1200423651`.
- [ ] **1.2. Group ID** (`UniqueID Type="9"`)
  - Hiển thị đúng mã nhóm: `GRP-9988421` (nếu có).
- [ ] **1.3. Booking Status** (`ResStatus`)
  - Hiển thị trạng thái: `Confirmed`.
- [ ] **1.4. Booking Channel** (`BookingChannel`)
  - Hiển thị rõ nguồn OTA: mã kênh `BGC`.
- [ ] **1.5. Booking Timestamps**
  - `CreateDateTime`: `16/11/2026 17:01:52`.
  - Hiển thị chính xác `LastModifyDateTime`.

---

## MODULE 2. ROOM ALLOCATION & ROOM TYPES
*Cấu trúc phòng và loại phòng*

- [ ] **2.1. Total Rooms**
  - Hiển thị đúng **02 phòng độc lập**.

- [ ] **2.2. Room 1** (`IndexNumber="2029032"`)

  | Field | Expected Value |
  |---|---|
  | RoomTypeCode | `5001574` |
  | Room Type | Executive Family Suite |
  | InvBlockCode | `5000456` |
  | Quantity | 1 |

- [ ] **2.3. Room 2** (`IndexNumber="2029033"`)

  | Field | Expected Value |
  |---|---|
  | RoomTypeCode | `5001580` |
  | Room Type | Deluxe Double |
  | InvBlockCode | `5000456` |
  | Quantity | 1 |

---

## MODULE 3. GUEST BREAKDOWN & BEDDING
*Phân bổ khách lưu trú và cơ cấu giường*

- [ ] **3.1. Room 1 – Guest Breakdown (Total: 5 Guests)**

  | Guest Type | Quantity | Details | ResGuestRPH |
  |---|---:|---|---|
  | AdultBed | 2 | Người lớn, giường tiêu chuẩn | 1, 2 |
  | AdultExtraBed | 1 | Người lớn, giường phụ | 3 |
  | ChildBandBed | 1 | Trẻ em 8 tuổi, có giường phụ | 4 |
  | ChildBandWithoutBed | 1 | Trẻ em 3 tuổi, chung giường | 5 |

- [ ] **3.2. Room 2 – Guest Breakdown (Total: 2 Guests)**

  | Guest Type | Quantity | Details | ResGuestRPH |
  |---|---:|---|---|
  | AdultBed | 1 | Người lớn, giường tiêu chuẩn | 6 |
  | ChildBandWithoutBed | 1 | Em bé 1 tuổi, chung giường | 7 |

---

## MODULE 4. PRICING, RATEMIX & DISCOUNTS
*Giá phòng, gói giá, RateMix và chiết khấu*

- [ ] **4.1. Room 1 – Daily Rates**

  | Date | Rate Plan | Before Tax | After Tax |
  |---|---|---:|---:|
  | 16/12/2026 | `10011297` | 2,500,000 VND | 2,750,000 VND |
  | 17/12/2026 | `10011297` | 2,500,000 VND | 2,750,000 VND |

  **PlacementRates – Guest-level Price Breakdown**

  | Guest | Expected Rate |
  |---|---:|
  | Guest 1 – Adult | 1,000,000 VND |
  | Guest 2 – Adult | 1,000,000 VND |
  | Guest 3 – Adult Extra Bed | 500,000 VND |
  | Child | 250,000 VND |

- [ ] **4.2. Room 2 – Daily Rates (RateMix)**

  | Date | Rate Plan | After Tax |
  |---|---|---:|
  | 16/12/2026 | `10011297` | 1,650,000 VND |
  | 17/12/2026 | `10011298` | 1,980,000 VND |

  - [ ] Correctly identify the rate plan change from `10011297` to `10011298`.

- [ ] **4.3. Discounts & Promotions**

  | Field | Expected Value |
  |---|---|
  | Discount Code | `PROMO10` |
  | Discount Type | 10% |
  | Discount Amount | 550,000 VND |
  | Description | Giảm giá khuyến mãi mùa đông Early Bird 10% |

---

## MODULE 5. GUESTS VS. PAYER PROFILE
*Hồ sơ khách lưu trú thực tế và người thanh toán*

- [ ] **5.1. Actual Guests** (`ResGuests`)

  | RPH | Guest Name | Gender | Date of Birth | Nationality |
  |---|---|---|---|---|
  | 1 | John A. Smith | Male | 20/05/1985 | GBR |
  | 2 | Mary B. Smith | Female | 15/08/1988 | GBR |
  | 3 | David Smith | Male | 01/12/1990 | GBR |
  | 4 | Tommy Smith | Male | 10/03/2018 | GBR |
  | 5 | Alice Smith | Female | 01/09/2023 | GBR |
  | 6 | Emma Watson | Female | 11/11/1992 | USA |
  | 7 | Lily Watson | Female | 01/06/2025 | USA |

  **Loyalty Membership Information**

  - [ ] Hiển thị đầy đủ thông tin thẻ thành viên.

  | Field | Expected Value |
  |---|---|
  | Program | `EXELY_CLUB` |
  | Card Number | `VIP-998811` |
  | Membership Tier | `GOLD` |
  | Points Balance | 12,500 Points |

- [ ] **5.2. Payer / Customer Profile**

  | Field | Expected Value |
  |---|---|
  | Payer Name | John A. Smith |
  | Phone | `+447000000000` |
  | Email | guest.booking@example.com |
  | Street | Central Street 10 |
  | City | London |
  | Postal Code | SW1A 2AA |
  | Country | United Kingdom (GBR) |

---

## MODULE 6. GUARANTEES, DEPOSITS & PAYMENT GATEWAY
*Thanh toán, đặt cọc và cổng thanh toán*

- [ ] **6.1. Guarantee & Payment Information**

  | Field | Expected Value |
  |---|---|
  | GuaranteeCode | `PrePay` |
  | PaymentMethodName | `BankCard` |
  | PaymentSystemName | `TLPAYMENTS` |
  | PaymentSystemTitle | Thanh toán trực tuyến qua thẻ ngân hàng Cổng Exely |
  | PaymentSystemProfileAcquiringName | `Hotel` |
  | PaymentTransactionId | `TXN-20261216-99881234` |

  - [ ] Correctly identify `Hotel` acquiring type (payment transferred directly to the hotel's account).

- [ ] **6.2. Deposit & Payment Transactions** (`DepositPayments`)

  | Payment | Type | PaymentIndex | Amount |
  |---|---|---:|---:|
  | Deposit 1 | ReceivedPayment | 0 | 3,000,000 VND |
  | Deposit 2 | ReceivedPayment | 1 | 2,000,000 VND |
  | Loyalty Payment | ReceivedLoyaltyPayment | – | 500,000 VND |

  **Payment Summary**

  | Description | Expected Amount |
  |---|---:|
  | Total Paid | **5,500,000 VND** |
  | Balance Due at Check-in | **4,630,000 VND** |

  - [ ] Deposit 1 correctly recorded in the first cashbook entry.
  - [ ] Deposit 2 correctly recorded in the second cashbook entry.
  - [ ] Loyalty payment correctly recorded as a reward-points payment.
  - [ ] Total paid and outstanding balance are displayed correctly.

---

## MODULE 7. SERVICES & ADDITIONAL CHARGES
*Dịch vụ đi kèm, phụ phí, Early Check-in và Late Check-out*

- [ ] **7.1. Breakfast Buffet** (`ServiceRPH="1"`)

  | Field | Expected Value |
  |---|---|
  | Service Name | Breakfast Buffet |
  | Inclusive | `true` |
  | Price | 0 VND |
  | Quantity | 5 servings |
  | Duration | 2 days |

- [ ] **7.2. Airport Transfer** (`ServiceRPH="2"`, `ServiceCategoryCode="Transfer"`)

  | Field | Expected Value |
  |---|---|
  | Service Name | Xe đưa đón sân bay |
  | Amount After Tax | 500,000 VND |
  | Amount Before Tax | 454,545 VND |
  | Pickup Location | Noi Bai Airport |
  | Pickup Time | 14:30 |
  | Flight Number | VN212 |
  | Vehicle | 7-seat Ford Transit |

- [ ] **7.3. Early Check-in** (`ServiceRPH="3"`, `ServiceInventoryCode="EarlyArrival"`)

  | Field | Expected Value |
  |---|---|
  | Service Name | Early Check-in |
  | Amount After Tax | 300,000 VND |
  | Expected Check-in | 08:00 AM, 16/12/2026 |

- [ ] **7.4. Late Check-out** (`ServiceRPH="4"`, `ServiceInventoryCode="LateDeparture"`)

  | Field | Expected Value |
  |---|---|
  | Service Name | Late Check-out |
  | Amount After Tax | 200,000 VND |
  | Expected Check-out | 16:00 PM, 18/12/2026 |

---

## MODULE 8. CANCELLATION POLICIES & SPECIAL REQUESTS
*Chính sách hủy phòng và yêu cầu đặc biệt*

- [ ] **8.1. Cancellation Policy** (`CancelPenalties`)

  | Field | Expected Value |
  |---|---|
  | Free Cancellation Deadline | `15/12/2026 07:00:00Z` |
  | Late Cancellation Penalty | 1 night |
  | Penalty Amount | 2,750,000 VND |

  **Policy Description:**

  > Hủy phòng trước 24h so với 14:00 ngày nhận phòng miễn phí. Hủy dưới 24h tính phí 1 đêm đầu tiên.

- [ ] **8.2. Special Requests** (`SpecialRequest`)

  > Khách muốn kê phòng tầng cao, giường phụ kê cạnh cửa sổ, hỗ trợ 01 nôi em bé cho Phòng 2.

  - [ ] Hiển thị chính xác toàn bộ nội dung yêu cầu đặc biệt.
  - [ ] Không bị mất hoặc cắt ngắn nội dung ghi chú.

- [ ] **8.3. Room Type Meal Plan** (`RoomTypeMealPlan`)

  > Bao gồm ăn sáng Buffet hàng ngày cho tất cả các khách lưu trú.

  - [ ] Hiển thị đúng nội dung gói ăn.
  - [ ] Đảm bảo thông tin được gắn đúng với booking.

---

## TEST COMPLETION SUMMARY

| Module | Description | Status |
|---|---|---|
| 1 | Booking Header & Metadata | ⬜ Pending |
| 2 | Room Allocation & Types | ⬜ Pending |
| 3 | Guest Breakdown & Bedding | ⬜ Pending |
| 4 | Pricing, RateMix & Discounts | ⬜ Pending |
| 5 | Guests vs. Payer Profile | ⬜ Pending |
| 6 | Guarantees & Deposits | ⬜ Pending |
| 7 | Services & Additional Charges | ⬜ Pending |
| 8 | Policies & Special Requests | ⬜ Pending |

**Overall Result:** Pending

**Notes:** All fields should be verified against the original Exely XML payload and their corresponding display locations in HBSoft PMS.
