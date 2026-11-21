# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Nguyễn Hán Trường Giang        Người kiểm (học viên): Bùi Lê Đình Văn (2A202603124)
Ngày: 2026-11-21                                      Phiên bản guideline: Road v1.0
File được kiểm (tên + `revision` trong manifest): nguyenhantruonggiang-front.zip, nguyenhantruonggiang-fisheye.zip (revision 1)
Số ảnh kiểm: 6 (+ 0 ảnh thêm, ghi riêng)               Số nhãn đã kiểm (shape + tag): 60

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 24 | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 6 | 0 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 6 | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 6 | 0 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 6 | 1 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 6 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 6 | 0 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 5 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 4 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 4 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 2 | 1 | chính |
| QC1-12 file | lỗi file | 2 | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-05 | `A04_b7a8e795-0ff55db2.jpg` | `lane` (`position=L1, kind=double`) | chính | Vạch đôi gồm 2 polyline song song có cùng `position=L1` (cần đối chiếu quy tắc vạch đôi/cảnh báo trùng `position`) |
| 2 | QC1-11 | `B01_02688_FV.png` | `crosswalk`, `drivable` | chính | Polygon `crosswalk` và `drivable` ở vùng lề dưới fisheye chồng lấn/biên sát nhau cần rà lại đường biên/độ cong |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| `A04_b7a8e795-0ff55db2.jpg` | Hai nét vạch đôi `kind=double` cùng `position=L1` có tính là lỗi `QC1-05` hay hợp lệ theo vạch đôi? | Đối chiếu theo Guideline Road v1.0 khi chốt kết quả lô |
| `B01_02688_FV.png`, `B02_03177_FV.png` | Biên `crosswalk` và `drivable` ở vùng mép/góc fisheye có cần tinh chỉnh thêm độ cong cho khớp guideline không? | Đối chiếu trực tiếp trên ảnh gốc theo Road v1.0 |

## Quyết định
Lỗi nặng: 0   Lỗi chính: 2 / 60 nhãn = 3.33 %   Lỗi nhẹ: 0   Ca chờ lead: 0
Quyết định (Release / Hold / Rework): Release
Lý do (theo luật của phiếu): Không có lỗi nặng, tỉ lệ lỗi chính là 2 / 60 = 3.33 % (<= 5 % trên tổng số nhãn đã kiểm) và không có ca mơ hồ chờ lead -> Release.

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](../docs/qc_severity_road_v1.0.md).
