//
//  PhoneUILabel.swift
//
//  Created by Jorge Cordero Sanchez on 18/5/17.
//  Copyright © 2017 Jorge Cordero Sanchez. All rights reserved.
//
import UIKit

@IBDesignable
class PhoneUILabel: UILabel{
    
    @IBInspectable
    var phone: String?{
        didSet{
            let tap = UITapGestureRecognizer(target: self, action: #selector(self.onLabelClic(sender:)))
            self.isUserInteractionEnabled = true
            self.addGestureRecognizer(tap)
        }
    }
    
    override func drawText(in rect: CGRect) {
        super.drawText(in: rect)
        // Tap serviceConditions handler
        let tap = UITapGestureRecognizer(target: self, action: #selector(self.onLabelClic(sender:)))
        self.isUserInteractionEnabled = true
        self.addGestureRecognizer(tap)
    }
    
    private func openPhoneCall(phoneNumber: String!) {
        let phoneCallURL = URL(string: "tel://\(phoneNumber.replacingOccurrences(of: " ", with: ""))")
        if phoneCallURL != nil {
            
            let application:UIApplication = UIApplication.shared
            if (application.canOpenURL(phoneCallURL!)) {
                application.open(phoneCallURL!, options: [:], completionHandler: nil)
            }
        }
    }
    
    @objc func onLabelClic(sender:UITapGestureRecognizer) {
        self.openPhoneCall(phoneNumber: phone)
    }
}
